### function --fileupload  上传文档
```
 namespace KitBaseBundle\Service;
 
 use Symfony\Component\HttpFoundation\File\UploadedFile;
 
 class FileUploader
 {
     private $targetDir;
 
     public function __construct($targetDir)
     {
         $this->targetDir = $targetDir;
     }
 
     public function upload(UploadedFile $file, $subDir = '')
     {
         $fileName = md5(uniqid()).'.'.$file->guessExtension();
         $subDir = empty($subDir) ? '' : '/' . $subDir;
         $file->move($this->targetDir . $subDir, $fileName);
 
         return $subDir . '/' .$fileName;
     }
 }

```

### function 对code字段截取设给pCode
```
 public function textAction(){
        $repository = $this->getDoctrine()->getRepository('KitCaseBundle:Institutions');
        $data = $repository->findAll();
        $em = $this->getDoctrine()->getManager();
        foreach($data as $k => $v){
            $code = $v->getCode();
            $v->setPCode(substr($code,0,6));
            $em->persist($v);
            dump(substr($code,0,6));
        }
        $em->flush();
        return new JsonResponse([
            'text' => 123
        ]);
    }
```
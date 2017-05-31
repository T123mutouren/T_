
* getCount
** count 为sql保留字段不能使用
>  public function getCount(parameter_where){
>      	$qb = $this->createQueryBuilder('name');
>       reeturn $qb->select('count(name) as num')
>          ->where('name.where =:where')
>          ->setParameter('where',$parameter_where)
>          ->getQuery()
>          ->getSingleScalarResult();
>  }

* getCount
** count 为sql保留字段不能使用

>  public function getCount(parameter_where){
>  //parameter_where 为条件字段的参数
>      	$qb = $this->createQueryBuilder('name');
>       reeturn $qb->select('count(name) as num')
>          ->where('name.where =:where')
>  // where 为条件字段
>          ->setParameter('where',$parameter_where)
>          ->getQuery()
>          ->getSingleScalarResult();
>  }
## doctrine 

* 开启服务：

		php bin/console server:run

* 创建库

		php bin/console doctrine:database:create

* 创建Entity

		php bin/console doctrine:gentrate:entity BundleName:tablaName

* 生成get|set方法

		php bin/console doctrine:generate:entities BundleName

* 检测、生成表

		php bin/console doctrine:schema:update --dump-sql

		php bin/console doctrine:schema:update --force

* 周期管理工具（自动完成）
>  `*@ORM\HasLifecycleCallbacks();`

> prePersist() 提交数据时执行

> preUpdate() 修改数据时执行

* 多表关联
> 双向关系，相互get，对数据库有压力，外键放入常用表
>> *@ManyToOne(targetEntity="（关联Entity）",inversedBy="（关联键名）")

>> *@JoinColumn(name="（外键名）",referencedColumnName="id")

>> *@OneToMany(targetEntity="profile",mappedBy="user")

* 实例化对象
		$obj = new obj() //entity

* 持久化对象

		 $em = $this->getDoctrine->getManager();
		 $em->persist();

* 提交数据

		 $em->flush();

* 结果数量限制
 
		$qb->setMaxResult($limit);

* 获取刚插入数据的id 

		$this->getConnection()->lastInsertId();

* 初始化处理

		php bin/console doctrine:fixtures:load --append(执行默认)

		php bin/console doctrine:fixtures:load --append --fixtures=path（执行指定的文件，可执行多个。）

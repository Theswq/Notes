### POJO

- 全称为：Plain Ordinary Java Object，普通的 java 对象，一般用在数据层映射到数据库表的类，类的属性与表字段一一对应

### PO

- 全称为：Persistant Object，持久化对象，与数据库结构映射的实体，数据库中的一条数据即为一个 BO 对象

### BO

- 全称为：Business Object，业务对象，主要作用是把业务逻辑封装成一个对象，这个对象可以包括一个或多个其它对象，比如一个简历 BO 中有教育经历，工作经历，社会关系等 PO 对象

### DTO

- 全称为：Data Transfer Object，数据传输对象，比如一张表有 100 个字段，那么对应的 PO 就有100 个属性（大多数情况下，DTO内部的数据结构来自多个表）但 view 层只需要显示 10 个字段，没有必要把整个 PO 对象传递到 client，这时我们就可以用只有这 10 个属性的 DTO 来传输给 client，这样也不会暴露 server 端表结构，到达客户端后，如果这个对象来对应页面显示，它的身份就转为 VO

### VO

- 全称为：View Object，主要对应页面展示的数据对象，一般继承自 PO，可以添加 PO 中没有的字段，用来逻辑处理以及其它消息存储

### DO

- 全称为：Domain Object，领域对象，从现实世界中抽象出的业务实体，一般还包含 ORM 映射

### DAO

- 全称为：Data Access Object，数据访问对象，一般所说的 DAO 层，用于连接数据库与外层之间的桥梁，并持久化数据层对象

### JavaBean

- JavaBean 是一种 Java 语言写成的可重用组建，它的规范必须符合特定的约定： 
  - 这个类必须有一个公共的缺省构造函数
  - 这个类的属性用 getter 和 setter 访问
  - 这个类可被序列化

### 模型

- 用户发出请求，表单的数据层被匹配为 VO
- 展示层把 VO 转换为服务层对应方法锁要求的 DTO，传输给服务层
- 服务层首先根据 DTO 的数据构造一个 DO，调用 DO 的业务方法完成具体业务
- 服务层把 DO 转换为持久层对应的 PO，调用持久层持久化方法，把 PO 传递给它完成持久化操作
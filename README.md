# node-web-api
Collection of web apis with nodejs


The following table shows overview of the Rest APIs that will be exported:

| Methods | Urls                     | Actions                                      |
| ------- | ------------------------ | -------------------------------------------- |
| GET     | api/tutorials            | get all Tutorials                            |
| GET     | api/tutorials/:id        | get Tutorial by id                           |
| POST    | api/tutorials            | add new Tutorial                             |
| PUT     | api/tutorials/:id        | update Tutorial by id                        |
| DELETE  | api/tutorials/:id        | remove Tutorial by id                        |
| DELETE  | api/tutorials            | remove all Tutorials                         |
| GET     | api/tutorials/published  | find all published Tutorials                 |
| GET     | api/tutorials?title=[kw] | find all Tutorials which title contains 'kw' |

- Download mysql
- Create database called testdb
- Create table as follows
  
`
CREATE TABLE IF NOT EXISTS `tutorials` (
  id int(11) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  title varchar(255) NOT NULL,
  description varchar(255),
  published BOOLEAN DEFAULT false
) ENGINE=InnoDB DEFAULT CHARSET=utf8;`
`

## Test flow
> use ThundeClient

#### Create multiple entries as follows
> sample with publish true

`
{
  "title": "express api",
  "description": "Description 2",
  "published": true
}`

> sample with publish false

`
{
  "title": "node api",
  "description": "Description 1",
}`


#### In Development force sync DB

`db.sequelize.sync({ force: true }).then(() => {
  console.log("Drop and re-sync db.");
});`


### Resources
> https://www.mysqltutorial.org/

> https://www.bezkoder.com/node-js-rest-api-express-mysql/

> https://www.npmjs.com/package/mysql

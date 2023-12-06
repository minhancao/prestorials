# Demo

1. Go to Podman Desktop, click on the Containers tab on the left side, and click on the coordinator container
<img width="1041" alt="image" src="https://github.com/minhancao/prestorials/assets/36718441/5ab4011d-ab8c-462c-853f-122c5b9a4aa4">

2. Click on the Terminal tab and in the Terminal invoke the presto-cli by typing `presto-cli` and press enter.
<img width="1041" alt="image" src="https://github.com/minhancao/prestorials/assets/36718441/708ee0f2-4d93-49a0-845f-3b8ac8855366">

You can now play around with the Docker setup with Presto coordinator and Velox workers!


## Some queries to try
`select * from system.runtime.nodes;`

`show catalogs;`

`use hive.default;`

`show schemas;`

For the create table query below, please first create an empty bucket named `demo-bucket` in your MinIO storage using the UI http://localhost:9000.

`create table demo(id varchar, fname varchar, lname varchar) with (format = 'PARQUET', external_location = 's3a://demo-bucket/');`

`insert into demo values('1', 'donald', 'duck');`

`select * from demo;`

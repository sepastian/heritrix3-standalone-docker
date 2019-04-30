This uses the `heritrix-worker` image by ukwa.

# Usage

``` shell
docker-compose up
```

Go to https://localhost:8443.
_Note, its `https`, not `http`._

Login with `admin`/`admin`, configure credentials in `docker-compose.yml` by setting `HERITRIX_USERNAME` and `HERITRIX_PASSWORD`, respectively.

## Jobs

Create a new job `my-job` in Heritrix's web interface.
This will create the folder `./jobs/my-job`.
Configure the crawl job by editing `./jobs/my-job/crawler-beans.xml`.

Start the jobs through the web interface (_build_, _launch_, reload page, _unpause_).
Each crawl will create a folder named `./jobs/my-job/<YYYYMMDD>`;
in addition, `./jobs/my-job/latest` will point at just that.

Clicking _checkpoint_ will create a gzipped WARC file under `./jobs/my-job/latest/warcs`;
when the job has finished, such a WARC file will be created, too.

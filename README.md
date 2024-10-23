# MyCharts
MyCharts is a chart creation SaaS application, designed with a microservices architecture. It was created as part of the Software-as-a-Service Technologies class of the [School of Electrical and Computer Engineering](https://www.ece.ntua.gr/en) of the [National Technical University of Athens](https://ntua.gr/en/) during the academic year 2022-2023.

#### Contributors
* `dimjimitris` - Dimitris Georgousis
* `gkapetanakis` - George Kapetanakis (me)
* `ntua-el19008` - Ioannis Protogeros

#### Grade
The project was graded with a 10 out of 10.

#### Project Description
The project description in Greek, along with all other provided files, can be found in the `handouts` folder.

## How To Run:
* Clone repo to an empty folder. `cd` to that folder.
* `cd docker_compose`
* `docker build -t puppeteer .`
* Recommended way to run (frontend running locally):
  * `docker compose up`
  * `cd ../frontend`
    * If you are on an (M1/M2) Mac:
    * `brew install cairo`
    * `brew install pango`
  * `npm install`
  * `npm run dev`
  * Frontend is now listening on `http://localhost:3000`
  * `docker compose down` when you are done (or stop it AND delete it from the desktop app)
* Not recommended way to run (frontend running dockerized):
  * `docker compose --profile frontend up`
  * Frontend is now listening on `http://localhost:3000`
  * `docker compose --profile frontend down` when you are done (or stop it AND delete it from the desktop app)

If the frontend is ran dockerized, it will be very slow and maybe even unresponsive due to the large number of containers running at the same time (at least it was on our computers). If your computer's architecture is `arm64`, be warned that due to some missing packages on `arm64` the frontend container is ran in a `linux/amd64` image (which will be extremely slow on your machine).

That's it.

Tools used: `Node.js`, `Next.js`, `Docker`, `Apache Kafka`, `MongoDB (Atlas)`, `Highcharts`.

Special thanks to the creator(s) of the `wurstmeister/zookeeper` and `wurstmeister/kafka` docker images.

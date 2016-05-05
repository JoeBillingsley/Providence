# Providence
Predicting good deadlines is hard. Wouldn't it be great if you could just plug in some details about a current project and a magic machine would tell you when it would be done? The Providence project is to use machine learning algorithms to try and build such a machine - or at least as close as we can manage.

## How does it work?
The core algorithm is fairly simple it just takes your best estimate and [doubles it](http://xkcd.com/1658/). Well it's a little more complex than that but not too much. It's based on work by [Shan He and Leandro Minku](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.301.5198&rep=rep1&type=pdf) who applied machine learning algorithms to software effort datasets to build models that could predict the effort of future projects. The algorithm uses a multi-objective algorithm to optimise for different error metrics simueltaneously which smooths over problems with the individual metrics. After running it for some number of generations the best non-dominated solution for each metric goes into an ensemble. When a new project comes in the project is fed to each of the members in the ensemble and the average effort over all of the predictions is produced.

## How do I use it?
The project comes bundled with a gradle helper so you can compile and run the tool with a single command.

#### Windows
```shell
gradlew execute −x test 
```

#### Linux
```shell
 ./gradlew execute −x test 
```

# Shared community maintained TPV database

A shared database of rules for [Total Perspective Vortex](https://github.com/galaxyproject/total-perspective-vortex) used by the usegalaxy.* federation.


## List of recommended tags

|      tag | description |
|----------|-------------|
|upload   | for scheduling jobs to a upload worker |
|gpu| needs a GPU installed on the workder|
|docker| a Docker configured worker|
|docker_shell_access| the user will get shell access in Docker |
|singularity| a Singularity configured worker|

## Tips

Values are evaluated as Python f-strings, this means if you want to reference the number of `cores` you need to use quoted references like `       OMP_NUM_THREADS: "{cores}"`

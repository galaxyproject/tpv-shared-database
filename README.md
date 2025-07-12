# Shared community maintained TPV database

A shared database of rules for [Total Perspective Vortex](https://github.com/galaxyproject/total-perspective-vortex) used by the usegalaxy.* federation.

### Version Guide

| version | url                                                     | description                                        |
|---------|---------------------------------------------------------| ---------------------------------------------------|
| latest  | https://gxy.io/tpv/db-latest.yml                        | always points to latest version                    | 
| v2      | https://gxy.io/tpv/db-v2.yml                            | latest stable with minor revisions automatically included (recommended url). Currently an alias for latest, but gives you control over upgrade cycle. |
| v1      | https://gxy.io/tpv/db.yml, https://gxy.io/tpv/db-v1.yml | initial version                                    |


### Migration guide

#### From v1.x to 2.x

The TPV-Shared-DB v2 has some minor breaking changes.

* Ids for shared rules defined in the db have been prepended with 'tpvdb_' for better insight into provenance. If you're overriding any rules, you will need to adjust any rule ids accordingly. (https://github.com/galaxyproject/tpv-shared-database/pull/86)
* The shared db no longer defines mandatory tags like require docker. All require tags have been replaced with prefer (https://github.com/galaxyproject/tpv-shared-database/pull/87/files)
* Required docker tags have been dropped for three recetox tools (https://github.com/galaxyproject/tpv-shared-database/pull/85)


### Tips

Values are evaluated as Python f-strings, this means if you want to reference the number of `cores` you need to use quoted references like
`OMP_NUM_THREADS: "{cores}"`

### List of recommended tags

| tag                | description |
|--------------------|-------------|
|upload              | for scheduling jobs to a upload worker |
|docker              | a Docker configured worker |
|docker-shell-access | the user will get shell access in Docker |
|singularity         | a Singularity configured worker |

Dashes are used as separators in tags instead of underscores.

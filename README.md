# Template on dev container with microsft's python container

Modified to install mamba in the docker env, as well as conda + pip direct install (in the docker file)


- Can be modfied to used pure devcontainer.json
    - Not recommended as, it seems the postCreatecommands is not cached. Would impact on startup time.
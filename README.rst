runapp
------

Allows to build and/or run your application using simple config file
in yaml format

Commonly used in deploys, dockers etc.


using
-----
run:

.. code-block:: bash

    runapp [<atributes>]

inside the folder with **run.yaml** configuration file

see also **runapp --help**

run.yaml example:
#################

.. code-block:: yaml

    build:
      commands:
        - pip install -r ./configs/requirements.${ENV}.txt
    run:
      maxRepeats: 5
      repeatDelay: 1
      commands:
        - gunicorn manage:app -c ./configs/gunicorn.${ENV}.py

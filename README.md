# Minimal Godot Engine Docker image

This image provides the official Linux headless builds of Godot Engine along with the official templates of version 3.1.

The primary application is for automating Godot Engine builds.

Godot Engine is located at ```/bin/godot``` and the templates are installed in ```/root/.local/share/godot/templates```.

### Usage example (Gitlab CI)

The source repository contains a ```Vagrantfile``` who provides Docker and Gitlab Runner. It can be used to test your Gitlab CI configuration (see ```.gitlab-ci.yml``` in the source repository):

    $ gitlab-runner exec docker <job name>
   
There is no need to register the runner first.

### Credits

Rafał Zawadzki: https://hub.docker.com/r/bluszcz/godot/

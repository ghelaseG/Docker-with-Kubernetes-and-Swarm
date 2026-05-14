# use the README.md file for requirements to build this image
# If you get stuck, the answer/ directory has the solution

FROM ubuntu:latest

RUN apt-get apache2-utils

ENTRYPOINT ["ab"]

CMD ["-n", "10", "-c", "2", "https://www.google.com/", "-n", "10"]


FROM gcc
COPY ./main.c /usr/src/myapp/
WORKDIR /usr/src/myapp/
RUN gcc -o myapp main.c
CMD ["./myapp"]
FROM alpine 
COPY ./hello_python.py /myscript/hello_python.py
WORKDIR /myscript
RUN apk update
RUN apk add bash
RUN apk add python3
CMD ["./hello_python.py"]

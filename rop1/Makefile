binary:
	gcc rop.c -o rop -fno-stack-protector

clean:
	rm rop

docker: binary
	docker build -t rop1 .

remote: docker
	docker run --rm -p "127.0.0.1:22226:22226" -it rop1

extract-libc: docker
	docker rm -f rop1_dummy
	docker create -ti --name rop1_dummy rop1
	docker cp rop1_dummy:/lib/x86_64-linux-gnu/libc-2.31.so ./libc-docker.so
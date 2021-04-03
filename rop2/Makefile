binary:
	gcc rop.c -g -o rop

clean:
	rm rop

docker: binary
	docker build -t rop2 .

remote: docker
	docker run --rm -p "127.0.0.1:22226:22226" -it rop2

extract-libc: docker
	docker rm -f rop2_dummy
	docker create -ti --name rop2_dummy rop2
	docker cp rop2_dummy:/lib/x86_64-linux-gnu/libc-2.31.so ./libc-docker.so
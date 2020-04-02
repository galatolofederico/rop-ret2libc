binary:
	gcc rop.c -o rop -fno-stack-protector

clean:
	rm rop

docker:
	docker build -t rop1 .

remote:
	docker run --rm -p "127.0.0.1:22226:22226" -it rop1
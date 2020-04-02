binary:
	gcc rop.c -g -o rop

clean:
	rm rop

docker:
	docker build -t rop2 .

remote:
	docker run --rm -p "127.0.0.1:22226:22226" -it rop2
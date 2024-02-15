.PHONY: test-runtime test-libs

# #######################################
# Testing isolated PHP libs + shared libs
# #######################################

test-runtime:
	docker run \
		-it \
		--rm \
		--platform linux/amd64 \
		-v $(CURDIR)/../libs/amazon-linux-2-v80/native/php:/var/task/php \
		-v $(CURDIR)/../libs/amazon-linux-2-v80/native/lib:/var/task/lib/ \
		-w /var/task \
		--entrypoint /bin/bash \
		-p 8000:8000 \
		public.ecr.aws/lambda/nodejs:18

test-libs:
	docker run \
		-it \
		--rm \
		--platform linux/amd64 \
		-v $(CURDIR)/../libs/amazon-linux-2-v80/native/php:/var/task/php \
		-v $(CURDIR)/../libs/amazon-linux-2-v80/native/lib:/var/task/lib/ \
		-v $(CURDIR):/srv \
		-w /srv \
		--entrypoint /bin/bash \
		public.ecr.aws/lambda/nodejs:18

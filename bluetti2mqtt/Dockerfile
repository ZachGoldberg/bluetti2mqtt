ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install bluetti_mqtt
RUN apk add --update --no-cache \
		bluez=5.65-r0 git \
	&& pip install git+https://github.com/ZachGoldberg/bluetti_mqtt.git@patch-2 \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]

#
# NOTE: THIS DOCKERFILE IS GENERATED VIA "apply-templates.sh"
#
# PLEASE DO NOT EDIT IT DIRECTLY.
#

FROM python:3.10-alpine3.15

RUN apk add --no-cache gnupg librsync

# https://pypi.org/project/duplicity/
# https://duplicity.gitlab.io/
ENV DUPLICITY_VERSION 1.0.1
# https://gitlab.com/duplicity/duplicity

RUN set -eux; \
	apk add --no-cache --virtual .build-deps gcc gettext-tiny libc-dev librsync-dev; \
	pip install --no-cache-dir \
		"duplicity == $DUPLICITY_VERSION" \
# https://pypi.org/project/b2sdk/
		'b2sdk ~= 1.14' \
# https://gitlab.com/duplicity/duplicity/-/blob/master/requirements.txt "backend libraries"
	; \
	apk del --no-network .build-deps; \
	duplicity --version

CMD ["duplicity", "--help"]

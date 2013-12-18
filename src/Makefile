
TOPDIR=../
include $(TOPDIR)/common.mk

ZCS_CORE_LIBS_USER=\
	zimbracommon.jar		\
	zimbrastore.jar			\
	zimbrasoap.jar			\
	zimbraclient.jar		\
	zimbra-native.jar		\
	zimbra-charset.jar		\
	commons-codec.jar		\
	commons-fileupload.jar		\
	commons-httpclient.jar		\
	json.jar			\
	slf4j-api.jar			\
	servlet-api.jar			\
	zcs-core-commons-dbcp.jar  \
	zcs-core-commons-pool.jar

ZCS_CORE_LIBS_ZIMLET=\
	zimbracommon.jar		\
	zimbrastore.jar			\
	zimbrasoap.jar			\
	zimbraclient.jar		\
	zimbra-native.jar		\
	zimbra-charset.jar		\
	commons-codec.jar		\
	commons-fileupload.jar		\
	commons-httpclient.jar		\
	json.jar			\
	slf4j-api.jar			\
	servlet-api.jar			\
    zcs-core-commons-dbcp.jar  \
	zcs-core-commons-pool.jar

ZCS_CORE_LIBS_ADMIN=\
	zimbracommon.jar		\
	zimbrastore.jar			\
	zimbrasoap.jar			\
	zimbraclient.jar		\
	zimbra-native.jar		\
	zimbra-charset.jar		\
	commons-codec.jar		\
	commons-fileupload.jar		\
	commons-httpclient.jar		\
	json.jar			\
	slf4j-api.jar			\
	servlet-api.jar			\
	zcs-core-commons-dbcp.jar  \
	zcs-core-commons-pool.jar

ZIMLET_USER_JARDIR=mailboxd/webapps/zimbra/WEB-INF/lib
ZIMLET_ZIMLET_JARDIR=mailboxd/webapps/zimlet/WEB-INF/lib
ZIMLET_ADMIN_JARDIR=mailboxd/webapps/zimbraAdmin/WEB-INF/lib
ZIMLET_SERVICE_JARDIR=mailboxd/webapps/service/WEB-INF/lib
ZIMLET_LIB_JARDIR=lib/jars

all:	build

build:	install

install:	$(JAR_FILE_NAME)
	@mkdir -p \
	    $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR)		\
	    $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR)		\
	    $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR)	\
	    $(IMAGE_ROOT)/$(ZIMLET_ZIMLET_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && \
	    ln -sf commons-codec-1.6.jar		commons-codec.jar		&& \
	    ln -sf commons-fileupload-1.2.2.jar		commons-fileupload.jar		&& \
	    ln -sf commons-httpclient-3.1.jar		commons-httpclient.jar		&& \
	    ln -sf servlet-api-2.5.jar			servlet-api.jar			&& \
	    ln -sf slf4j-api-1.6.4.jar			slf4j-api.jar			&& \
	    ln -sf commons-pool-1.6.jar			zcs-core-commons-pool.jar	&& \
	    ln -sf commons-dbcp-1.4.jar			zcs-core-commons-dbcp.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS_USER) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
	@cd $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS_ADMIN) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
	@cd $(IMAGE_ROOT)/$(ZIMLET_ZIMLET_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS_ZIMLET) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done

clean:
	@true

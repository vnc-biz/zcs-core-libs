
TOPDIR=../
include $(TOPDIR)/common.mk

ZCS_CORE_LIBS_ZIMLET=\
	zimbracommon.jar		\
	zimbrastore.jar			\
	zimbrasoap.jar			\
	zimbraclient.jar		\
	commons-fileupload-1.2.1.jar	\
	json.jar			\
	slf4j-api-1.6.1.jar		\
	zcs-core-javamail.jar		\
	zcs-core-jaxen.jar		\
	zcs-core-xerces-impl.jar	\
	zcs-core-commons-pool.jar	\
	zcs-core-commons-dbcp.jar	\
	commons-httpclient-3.1.jar

ZCS_CORE_LIBS_ADMIN=\
	zcs-core-commons-pool.jar	\
	zcs-core-commons-dbcp.jar	\
	zcs-core-jaxen.jar		\
	zcs-core-xerces-impl.jar	\
	zcs-core-commons-pool.jar	\
	zcs-core-commons-dbcp.jar

ZCS_CORE_LIBS_USER=\
	zcs-core-commons-pool.jar	\
	zcs-core-commons-dbcp.jar	\
	zcs-core-jaxen.jar		\
	zimbrasoap.jar			\
	zcs-core-xerces-impl.jar	\
	zcs-core-commons-pool.jar	\
	zcs-core-commons-dbcp.jar

ZIMLET_USER_JARDIR=mailboxd/webapps/zimbra/WEB-INF/lib
ZIMLET_ZIMLET_JARDIR=mailboxd/webapps/zimlet/WEB-INF/lib
ZIMLET_ADMIN_JARDIR=mailboxd/webapps/zimbraAdmin/WEB-INF/lib
ZIMLET_SERVICE_JARDIR=mailboxd/webapps/service/WEB-INF/lib
ZIMLET_LIB_JARDIR=lib/jars

all:	build

build:	install

install:	$(JAR_FILE_NAME)
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf commons-codec-1.4.jar		commons-codec.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf commons-fileupload-1.2.1.jar	commons-fileupload.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf commons-httpclient-3.1.jar	commons-httpclient.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf slf4j-api-1.6.1.jar		slf4j-api.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf commons-pool-1.5.5.jar		zcs-core-commons-pool.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf commons-dbcp-1.4.jar		zcs-core-commons-dbcp.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf mail.jar			zcs-core-javamail.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf jaxen-1.1.1.jar		zcs-core-jaxen.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf xercesImpl-2.9.1.jar		zcs-core-xerces-impl.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf commons-pool-1.5.5.jar		zcs-core-commons-pool.jar
	@cd $(IMAGE_ROOT)/$(ZIMLET_LIB_JARDIR) && ln -sf commons-dbcp-1.4.jar		zcs-core-commons-dbcp.jar
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS_USER) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS_ADMIN) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_ZIMLET_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_ZIMLET_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS_ZIMLET) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done

clean:
	@true

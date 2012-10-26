
TOPDIR=../
include $(TOPDIR)/common.mk


ZCS_CORE_LIBS_ZIMLET=\
	zimbracommon.jar		\
	zimbrastore.jar			\
	zimbrasoap.jar			\
	zimbraclient.jar		\
	commons-fileupload-1.2.1.jar	\
	json.jar			\
	slf4j-api-1.6.1.jar             \
    commons-httpclient-3.1.jar

ZCS_CORE_LIBS_ADMIN=\
	zimbrasoap.jar

ZCS_CORE_LIBS_USER=\
	zimbrasoap.jar


ZIMLET_USER_JARDIR=mailboxd/webapps/zimbra/WEB-INF/lib
ZIMLET_ZIMLET_JARDIR=mailboxd/webapps/zimlet/WEB-INF/lib
ZIMLET_ADMIN_JARDIR=mailboxd/webapps/zimbraAdmin/WEB-INF/lib
ZIMLET_SERVICE_JARDIR=mailboxd/webapps/service/WEB-INF/lib
ZIMLET_LIB_JARDIR=lib/jars

all:	build

build:	install

install:	$(JAR_FILE_NAME)
	@true
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


TOPDIR=../
include $(TOPDIR)/conf.mk

ZCS_CORE_LIBS=\
	log4j-1.2.16.jar	\
	zimbracommon.jar	\
	zimbrastore.jar		\
	zimbrasoap.jar		\
	mail.jar		\
	commons-logging.jar

ZIMLET_USER_JARDIR=mailboxd/webapps/zimbra/WEB-INF/lib
ZIMLET_ADMIN_JARDIR=mailboxd/webapps/zimbraAdmin/WEB-INF/lib
ZIMLET_SERVICE_JARDIR=mailboxd/webapps/service/WEB-INF/lib
ZIMLET_LIB_JARDIR=lib/jars

INSTALL_USER=y
INSTALL_ADMIN=y
INSTALL_SERVICE=y

all:	build

build:	install

install:	$(JAR_FILE_NAME)
	@true
ifeq ($(INSTALL_USER),y)
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
endif
ifeq ($(INSTALL_ADMIN),y)
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
endif
ifeq ($(INSTALL_SERVICE),y)
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_SERVICE_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_SERVICE_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
endif

clean:
	@true

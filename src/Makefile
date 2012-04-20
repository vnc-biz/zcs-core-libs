
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

build:	install_user install_admin install_service

ifeq ($(INSTALL_USER),y)
install_user:	$(JAR_FILE_NAME)
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_USER_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
else
install_user:
	@true
endif

ifeq ($(INSTALL_ADMIN),y)
install_admin:	$(JAR_FILE_NAME)
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_ADMIN_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
else
install_admin:
	@true
endif

ifeq ($(INSTALL_SERVICE),y)
install_service:	$(JAR_FILE_NAME)
	@mkdir -p $(IMAGE_ROOT)/$(ZIMLET_SERVICE_JARDIR)
	@cd $(IMAGE_ROOT)/$(ZIMLET_SERVICE_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS) ; do ln -sf ../../../../../$(ZIMLET_LIB_JARDIR)/$$i ; done
else
install_service:
	@true
endif


## this creates symlinks from /opt/zimbra for the libs into $HOME, for easier building
devel_symlinks:
	@mkdir -p $(HOME)/$(ZIMLET_LIB_JARDIR)
	@cd $(HOME)/$(ZIMLET_LIB_JARDIR) && \
	    for i in $(ZCS_CORE_LIBS) ; do ln -sf /opt/zimbra/$(ZIMLET_LIB_JARDIR)/$$i ; done

clean:
	@true

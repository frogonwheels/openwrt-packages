#
# Copyright (C) 2008-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=asterisk
PKG_VERSION:=1.6.2.14
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://downloads.digium.com/pub/asterisk/releases/
PKG_MD5SUM:=4f0414c9b2d449222b2fc7096cbaffe7

PKG_BUILD_DEPENDS:= libopenh323 pwlib gsm libvorbis

include $(INCLUDE_DIR)/package.mk

STAMP_CONFIGURED:=$(STAMP_CONFIGURED)_$(call confvar, \
	CONFIG_PACKAGE_asterisk16 CONFIG_PACKAGE_asterisk16-mini \
	CONFIG_PACKAGE_asterisk16-chan-alsa CONFIG_PACKAGE_asterisk16-chan-gtalk \
	CONFIG_PACKAGE_asterisk16-chan-h323 CONFIG_PACKAGE_asterisk16-chan-mgcp \
	CONFIG_PACKAGE_asterisk16-chan-skinny CONFIG_PACKAGE_asterisk16-codec-ilbc \
	CONFIG_PACKAGE_asterisk16-codec-lpc10 CONFIG_PACKAGE_asterisk16-codec-speex \
	CONFIG_PACKAGE_asterisk16-pbx-dundi CONFIG_PACKAGE_asterisk16-res-agi \
	CONFIG_PACKAGE_asterisk16-res-crypto CONFIG_PACKAGE_asterisk16-pgsql \
	CONFIG_PACKAGE_asterisk16-sqlite CONFIG_PACKAGE_asterisk16-voicemail \
	CONFIG_PACKAGE_asterisk16-sounds \
)

define Package/asterisk16/Default
  SUBMENU:=asterisk16 (Complete Open Source PBX), v1.6.x
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Asterisk
  URL:=http://www.asterisk.org/
  MAINTAINER:=Hans Zandbelt <hans.zandbelt@gmail.com>
endef

define Package/asterisk16/Default/description
 Asterisk is a complete PBX in software. It provides all of the features
 you would expect from a PBX and more. Asterisk does voice over IP in three
 protocols, and can interoperate with almost all standards-based telephony
 equipment using relatively inexpensive hardware.
endef

define Package/asterisk16-core
$(call Package/asterisk16/Default)
  TITLE:=Asterisk Core
  DEPENDS:=+libncurses +libpopt +libpthread @!TARGET_avr32
endef

define Package/asterisk16-core/description
$(call Package/asterisk16/Default/description)
Asterisk Core
  codec_gsm
  format_gsm
  pbx_config   Read Configuration
  res_indications Tone support
  app_dial
  chan_local Dial Local channel
endef

define Package/asterisk16
$(call Package/asterisk16/Default)
  TITLE:=Complete open source PBX
  DEPENDS:= +asterisk16-core +asterisk16-iax +asterisk16-sip +asterisk16-codec-ualaw +asterisk16-codec-wav +asterisk16-features +asterisk16-moh \
            +asterisk16-app-meetme +asterisk16-chan-oss +asterisk16-chan-alsa +asterisk16-chan-gtalk +asterisk16-chan-mgcp \
            +asterisk16-chan-skinny +asterisk16-codec-lpc10 +asterisk16-codec-speex +asterisk16-pbx-dundi +asterisk16-res-agi +asterisk16-res-crypto \
            +asterisk16-pgsql +asterisk16-sqlite +asterisk16-voicemail +asterisk16-sounds +asterisk16-rawplayer +asterisk16-agents +asterisk16-iax \
            +asterisk16-sip +asterisk16-codec-wav +asterisk16-codec-ualaw +asterisk16-format-misc +asterisk16-format-licensed +asterisk16-codec-g726 \
            +asterisk16-format-video +asterisk16-variables +asterisk16-enum +asterisk16-basic +asterisk16-encode +asterisk16-realtime \
            +asterisk16-ael +asterisk16-adsi +asterisk16-features +asterisk16-moh +asterisk16-smdi +asterisk16-sounds-tt \
            +asterisk16-sounds-demo +asterisk16-linejack +asterisk16-app-misc +asterisk16-image +asterisk16-sms +asterisk16-icecast \
            +asterisk16-mp3 +asterisk16-cli +asterisk16-deprecated +asterisk16-groups +asterisk16-spool \
            +asterisk16-nbs +asterisk16-alarmreceiver +asterisk16-cdr +asterisk16-channel +asterisk16-debug +asterisk16-menu-misc \
            +asterisk16-festival +asterisk16-send-app +asterisk16-followme +asterisk16-queues +asterisk16-record +asterisk16-privacy \
            +asterisk16-ivr-util +asterisk16-callerid +asterisk16-speech +asterisk16-detect +asterisk16-controlflow \
            @!TARGET_avr32 @!PACKAGE_asterisk14 @!PACKAGE_asterisk14-xip


endef

define Package/asterisk16/description
$(call Package/asterisk16/Default/description)
endef


define Package/asterisk16-mini
$(call Package/asterisk16/Default)
  TITLE:=Minimal open source PBX
  DEPENDS:=+libncurses +libpthread +asterisk16-core +asterisk16-iax +asterisk16-sip +asterisk16-codec-ualaw +asterisk16-codec-wav +asterisk16-features +asterisk16-moh +libgsm  @!TARGET_avr32
endef

define Package/asterisk16-mini/description
$(call Package/asterisk16/Default/description)
 This package contains only the following modules:
 - app_dial
 - chan_iax2
 - chan_local
 - chan_sip
 - codec_gsm
 - codec_ulaw
 - format_gsm
 - format_pcm
 - format_wav
 - format_wav_gsm
 - pbx_config
 - res_features
 - res_musiconhold
endef


define Package/asterisk16-app-meetme
$(call Package/asterisk16/Default)
  TITLE:=conferencing support
  DEPENDS:= +asterisk16-core +dahdi-libtonezone +kmod-dahdi-linux
endef

define Package/asterisk16-app-meetme/description
$(call Package/asterisk16/Default/description)
 This package provides the MeetMe application driver Conferencing support to 
 Asterisk.
   app_meetme
   app_page   Paging multiple extensions.
endef


define Package/asterisk16-chan-oss
$(call Package/asterisk16/Default)
  TITLE:=OSS soundcards support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-chan-oss/description
$(call Package/asterisk16/Default/description)
 This package provides the channel driver for OSS sound cards support to 
 Asterisk.
endef

define Package/asterisk16-chan-alsa
$(call Package/asterisk16/Default)
  TITLE:=ALSA soundcards support
  DEPENDS:= +asterisk16-core +alsa-lib
endef

define Package/asterisk16-chan-alsa/description
$(call Package/asterisk16/Default/description)
 This package provides the channel driver for ALSA sound cards support to 
 Asterisk.
endef


define Package/asterisk16-chan-gtalk
$(call Package/asterisk16/Default)
  TITLE:=GTalk support
  DEPENDS:= +asterisk16-core +libiksemel
endef

define Package/asterisk16-chan-gtalk/description
$(call Package/asterisk16/Default/description)
 This package provides the channel chan_gtalk and res_jabber for GTalk 
 support to Asterisk.
endef


define Package/asterisk16-chan-h323
$(call Package/asterisk16/Default)
  TITLE:=H.323 support for Asterisk
  DEPENDS:= +asterisk16-core +uclibcxx
endef

define Package/asterisk16-chan-h323/description
$(call Package/asterisk16/Default/description)
 This package provides H.323 support to Asterisk.
endef


define Package/asterisk16-chan-mgcp
$(call Package/asterisk16/Default)
  TITLE:=MGCP support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-chan-mgcp/description
$(call Package/asterisk16/Default/description)
 This package provides MGCP (Media Gateway Control Protocol) support \\\
 to Asterisk.
endef


define Package/asterisk16-chan-skinny
$(call Package/asterisk16/Default)
  TITLE:=Skinny Client Control Protocol support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-chan-skinny/description
$(call Package/asterisk16/Default/description)
 This package provided Skinny Client Control Protocol support to \\\
 Asterisk.
endef

define Package/asterisk16-chan-jingle
$(call Package/asterisk16/Default)
  TITLE:=Jingle Client support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-chan-jingle/description
Channel driver for Jingle client
endef

define Package/asterisk16-chan-unistim
$(call Package/asterisk16/Default)
  TITLE:=Unistim Client support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-chan-unistim/description
Channel driver for Unistim client
endef


#define Package/asterisk16-codec-ilbc
#$(call Package/asterisk16/Default)
#  TITLE:=ILBC Translator
#  DEPENDS:= +asterisk16-core
#endef

#define Package/asterisk16-codec-ilbc/description
#$(call Package/asterisk16/Default/description)
# This package contains the ILBC (Internet Low Bitrate Codec) translator 
# for Asterisk.
#endef


define Package/asterisk16-codec-lpc10
$(call Package/asterisk16/Default)
  TITLE:=LPC10 2.4kbps voice codec Translator
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-chan-lpc10/description
$(call Package/asterisk16/Default/description)
 This package contains the LPC10 (Linear Predictor Code) 2.4kbps voice 
 codec translator for Asterisk.
endef


define Package/asterisk16-codec-speex
$(call Package/asterisk16/Default)
  TITLE:=Speex/PCM16 Codec Translator
  DEPENDS:= +asterisk16-core +libspeex +libspeexdsp
endef

define Package/asterisk16-chan-speex/description
$(call Package/asterisk16/Default/description)
 This package contains the Speex speech compression codec translator for 
 Asterisk.
endef


define Package/asterisk16-pbx-dundi
$(call Package/asterisk16/Default)
  TITLE:=DUNDi support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-pbx-dundi/description
$(call Package/asterisk16/Default/description)
 This package provides DUNDi (Distributed Universal Number Discovery) 
 support to Asterisk.
endef


define Package/asterisk16-res-agi
$(call Package/asterisk16/Default)
  TITLE:=AGI support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-res-agi/description
$(call Package/asterisk16/Default/description)
 This package provides AGI (Asterisk Gateway Interface) support to 
 Asterisk.
endef


define Package/asterisk16-res-crypto
$(call Package/asterisk16/Default)
  TITLE:=Cryptographic Digital Signatures support
  DEPENDS:= +asterisk16-core +libopenssl
endef

define Package/asterisk16-res-crypto/description
$(call Package/asterisk16/Default/description)
 This package provides Cryptographic Digital Signatures support to 
 Asterisk.
 Includes AES functions.
endef


define Package/asterisk16-pgsql
$(call Package/asterisk16/Default)
  TITLE:=PostgreSQL support
  DEPENDS:= +asterisk16-core +libpq
endef

define Package/asterisk16-pgsql/description
$(call Package/asterisk16/Default/description)
 This package contains PostgreSQL support modules for Asterisk.
endef


define Package/asterisk16-sqlite
$(call Package/asterisk16/Default)
  TITLE:=SQLite modules
  DEPENDS:= +asterisk16-core +libsqlite2
endef

define Package/asterisk16-sqlite/description
$(call Package/asterisk16/Default/description)
 This package contains SQLite support modules for Asterisk.
endef


define Package/asterisk16-sounds
$(call Package/asterisk16/Default)
  TITLE:=Sound files
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-sounds/description
$(call Package/asterisk16/Default/description)
 This package contains sound files for Asterisk.
endef

define Package/asterisk16-voicemail-support
$(call Package/asterisk16/Default)
  TITLE:=Voicemail support functions
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-voicemail-support/description
Support functions for voicemail
  app_hasnewvoicemail Check for new voicemail
  func_vmcount	    Check for number of voicemails
endef

define Package/asterisk16-voicemail-mini
$(call Package/asterisk16/Default)
  TITLE:=Mini Voicemail support
  DEPENDS:= +asterisk16-core +asterisk16-adsi +asterisk16-voicemail-sounds-en
endef

define Package/asterisk16-voicemail-mini/description
$(call Package/asterisk16/Default/description)
  Minimal Voicemail System for Asterisk.  A voicemail system in small
  building blocks, working together based on the Comedian Mail voicemail system
endef

define Package/asterisk16-voicemail
$(call Package/asterisk16/Default)
  TITLE:=Comedian Mail voicemail support 
  DEPENDS:= +asterisk16-core +asterisk16-adsi +asterisk16-voicemail-sounds-en +asterisk16-voicemail-support
endef

define Package/asterisk16-voicemail/description
$(call Package/asterisk16/Default/description)
 This package contains the Comedian Mail voicemail related modules for Asterisk.
endef

define Package/asterisk16-voicemail-sounds-en
$(call Package/asterisk16/Default)
  TITLE:=English Sounds for Voicemail 
endef

define Package/asterisk16-voicemail-sounds-en/description
$(call Package/asterisk16/Default/description)
 English sounds for voicemail applications
endef

define Package/asterisk16-rawplayer
$(call Package/asterisk16/Default)
  TITLE:=Play raw files for asterisk
endef

define Package/asterisk16-rawplayer/description
 Contains the rawplayer utility for asterisk
endef

define Package/asterisk16-agents
$(call Package/asterisk16/Default)
  TITLE:=Support for user Agents
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-agents/description
$(call Package/asterisk16/Default/description)
Support for user Agents
  chan_agent
endef

define Package/asterisk16-iax
$(call Package/asterisk16/Default)
  TITLE:=IAX2 Channel support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-iax/description
$(call Package/asterisk16/Default/description)
IAX2 Channel support
  chan_iax2
endef

define Package/asterisk16-sip
$(call Package/asterisk16/Default)
  TITLE:=SIP Channel support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-sip/description
$(call Package/asterisk16/Default/description)
SIP Channel support
  chan_sip
endef

define Package/asterisk16-codec-wav
$(call Package/asterisk16/Default)
  TITLE:=WAV/PCM Codecs
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-codec-wav/description
$(call Package/asterisk16/Default/description)
WAV/PCM Codecs
  codec_adpcm
  format_pcm
  format_wav_gsm Microsoft Proprietary Wave GSM format
  format_wav
endef

define Package/asterisk16-codec-ualaw
$(call Package/asterisk16/Default)
  TITLE:=Ulaw/Alaw Codec support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-codec-ualaw/description
$(call Package/asterisk16/Default/description)
Ulaw/Alaw Codec support
  codec_alaw
  codec_a_mu A-Law and MUlaw direct coder/Decoder
  codec_ulaw
endef

define Package/asterisk16-format-misc
$(call Package/asterisk16/Default)
  TITLE:=Misc pass-through formats
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-format-misc/description
$(call Package/asterisk16/Default/description)
Misc pass-through formats
  format_sln
  format_sln16
  format_vox
  format_ilbc iLBC
  format_siren14
  format_siren7
endef

define Package/asterisk16-format-licensed
$(call Package/asterisk16/Default)
  TITLE:=Licenses and Patented Formats Passthrough
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-format-licensed/description
$(call Package/asterisk16/Default/description)
Licenses and Patented Formats Passthrough
  format_g726
  format_g723
  format_g729
endef

define Package/asterisk16-codec-g726
$(call Package/asterisk16/Default)
  TITLE:=G726 Codec (requires license)
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-codec-g726/description
$(call Package/asterisk16/Default/description)
G726 Codec (requires license)
  codec_g726
endef

define Package/asterisk16-codec-g722
$(call Package/asterisk16/Default)
  TITLE:=G722 Codec (requires license)
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-codec-g722/description
$(call Package/asterisk16/Default/description)
G722 Codec (requires license)
  codec_g722
endef

define Package/asterisk16-format-video
$(call Package/asterisk16/Default)
  TITLE:=Video formats
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-format-video/description
$(call Package/asterisk16/Default/description)
Video formats
  format_h263
  format_h264
endef

define Package/asterisk16-variables
$(call Package/asterisk16/Default)
  TITLE:=Read Variables and environment
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-variables/description
$(call Package/asterisk16/Default/description)
Read Variables and environment
  func_db
  func_global
  func_env
  func_timeout Control timeout values
endef

define Package/asterisk16-enum
$(call Package/asterisk16/Default)
  TITLE:=DNS Enum support to find alternate call route
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-enum/description
$(call Package/asterisk16/Default/description)
DNS Enum support to find alternate call route
  func_enum Use DNS to find alternate calling method
endef

define Package/asterisk16-basic
$(call Package/asterisk16/Default)
  TITLE:=Basic functions
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-basic/description
$(call Package/asterisk16/Default/description)
Basic functions
  func_logic
  func_math
  func_strings
  func_rand
  func_cut
  func_sprintf 
endef

define Package/asterisk16-encode
$(call Package/asterisk16/Default)
  TITLE:=Support for string encoding/hashing
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-encode/description
$(call Package/asterisk16/Default/description)
Support for string encoding/hashing
  func_base64
  func_md5
  func_sha1
  func_uri
endef

define Package/asterisk16-realtime
$(call Package/asterisk16/Default)
  TITLE:=Asterisk Realtime support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-realtime/description
$(call Package/asterisk16/Default/description)
Asterisk Realtime support
  func_realtime
  pbx_realtime
  res_realtime 'Realtime' support
endef

define Package/asterisk16-ael
$(call Package/asterisk16/Default)
  TITLE:=AEL - Asterisk Extension Language compiler support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-ael/description
$(call Package/asterisk16/Default/description)
AEL - Asterisk Extension Language compiler support
  pbx_ael Asterisk Extension Language compiler
  res_ael_share
endef

define Package/asterisk16-adsi
$(call Package/asterisk16/Default)
  TITLE:=ADSI Support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-adsi/description
$(call Package/asterisk16/Default/description)
ADSI Support
  res_adsi
  app_adsiprog
endef

define Package/asterisk16-features
$(call Package/asterisk16/Default)
  TITLE:=Call Features / Parking
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-features/description
$(call Package/asterisk16/Default/description)
Call Features / Parking
  res_features Features support.
  app_transfer
  app_parkandannounce
  res_monitor Record channels
endef

define Package/asterisk16-moh
$(call Package/asterisk16/Default)
  TITLE:=Music On Hold support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-moh/description
$(call Package/asterisk16/Default/description)
Music On Hold support
  res_musiconhold
endef

define Package/asterisk16-smdi
$(call Package/asterisk16/Default)
  TITLE:=Simple Message Desk Interface
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-smdi/description
$(call Package/asterisk16/Default/description)
Simple Message Desk Interface
  res_smdi Simple Message Desk Interface
endef

define Package/asterisk16-sounds-tt
$(call Package/asterisk16/Default)
  TITLE:=Telemarketer Torture Sounds
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-sounds-tt/description
$(call Package/asterisk16/Default/description)
Telemarketer Torture Sounds
endef

define Package/asterisk16-sounds-demo
$(call Package/asterisk16/Default)
  TITLE:=Demo Sounds
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-sounds-demo/description
$(call Package/asterisk16/Default/description)
Demo Sounds
endef

define Package/asterisk16-linejack
$(call Package/asterisk16/Default)
  TITLE:=M chan_phone (32,988) Linejack Cards 
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-linejack/description
$(call Package/asterisk16/Default/description)
M chan_phone (32,988) Linejack Cards 
endef

define Package/asterisk16-app-misc
$(call Package/asterisk16/Default)
  TITLE:=Misc applications
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-app-misc/description
$(call Package/asterisk16/Default/description)
Misc applications
  app_random
  app_sayunixtime
  app_sendtext
  app_url
  app_readfile
  app_system Call System application.
  app_exec Exec Dialplan applications
  func_shell	SHELL function to return the value of a system call.
endef

define Package/asterisk16-image
$(call Package/asterisk16/Default)
  TITLE:=Support for images
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-image/description
$(call Package/asterisk16/Default/description)
Support for images
  app_image Transmit images
  format_jpeg
endef

define Package/asterisk16-sms
$(call Package/asterisk16/Default)
  TITLE:=SMS support
  DEPENDS:= +asterisk16-core +libstdcpp
endef

define Package/asterisk16-sms/description
$(call Package/asterisk16/Default/description)
SMS support
  app_sms
endef

define Package/asterisk16-icecast
$(call Package/asterisk16/Default)
  TITLE:=ICEcast support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-icecast/description
$(call Package/asterisk16/Default/description)
ICEcast support
  app_ices Icecast / Ices support
endef

define Package/asterisk16-mp3
$(call Package/asterisk16/Default)
  TITLE:=MP3 Support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-mp3/description
$(call Package/asterisk16/Default/description)
MP3 Support
  app_mp3
endef

define Package/asterisk16-cli
$(call Package/asterisk16/Default)
  TITLE:=CLI Apps and events
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-cli/description
$(call Package/asterisk16/Default/description)
CLI Apps and events
  app_userevent
  res_clioriginate Originate a call on the CLI
  res_convert File format conversion
  res_clialiases Create aliases to other CLI commands.
endef

#define Package/asterisk16-isdn
#$(call Package/asterisk16/Default)
#  TITLE:=ISDN transfer capability
#  DEPENDS:= +asterisk16-core
#endef

#define Package/asterisk16-isdn/description
#$(call Package/asterisk16/Default/description)
#ISDN transfer capability
#  app_settransfercapability ISDN transfer capability
#endef

define Package/asterisk16-deprecated
$(call Package/asterisk16/Default)
  TITLE:=Deprecated
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-deprecated/description
$(call Package/asterisk16/Default/description)
Deprecated
  app_db Deprecated - use func_db instead
endef

define Package/asterisk16-groups
$(call Package/asterisk16/Default)
  TITLE:=Group Functions
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-groups/description
$(call Package/asterisk16/Default/description)
Group Functions
  func_groupcount
endef

define Package/asterisk16-spool
$(call Package/asterisk16/Default)
  TITLE:=Spool Directory of Outgoing calls
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-spool/description
$(call Package/asterisk16/Default/description)
Spool Directory of Outgoing calls
  pbx_spool Spool Directory of Outgoing calls
endef

define Package/asterisk16-nbs
$(call Package/asterisk16/Default)
  TITLE:=NBS stream support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-nbs/description
$(call Package/asterisk16/Default/description)
NBS stream support
  app_nbscat
endef

define Package/asterisk16-alarmreceiver
$(call Package/asterisk16/Default)
  TITLE:=SIA Contact ID Alarm receiver
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-alarmreceiver/description
$(call Package/asterisk16/Default/description)
SIA Contact ID Alarm receiver
  app_alarmreceiver
endef

define Package/asterisk16-cdr
$(call Package/asterisk16/Default)
  TITLE:=CDR Support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-cdr/description
$(call Package/asterisk16/Default/description)
CDR Support
  app_cdr
  app_forkcdr
  app_setcdruserfield
  cdr_csv
  cdr_custom
  cdr_manager
  func_cdr
endef

define Package/asterisk16-channel
$(call Package/asterisk16/Default)
  TITLE:=Channel functions
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-channel/description
$(call Package/asterisk16/Default/description)
Channel functions
  app_chanisavail
  app_channelredirect
  app_chanspy
  func_channel
  app_softhangup
  app_directed_pickup Pickup a (specific) ringing extensions
endef

define Package/asterisk16-debug
$(call Package/asterisk16/Default)
  TITLE:=Debugging tools
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-debug/description
$(call Package/asterisk16/Default/description)
Debugging tools
  app_echo
  pbx_loopback
  app_dumpchan Dump information about the calling channel
  app_verbose
  app_test AIX Server/client testing
endef

define Package/asterisk16-menu-misc
$(call Package/asterisk16/Default)
  TITLE:=Special menu applications
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-menu-misc/description
$(call Package/asterisk16/Default/description)
Special menu applications
  app_controlplayback
  app_playback
  app_directory
  app_dictate
endef

define Package/asterisk16-festival
$(call Package/asterisk16/Default)
  TITLE:=Festival support
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-festival/description
$(call Package/asterisk16/Default/description)
Festival support
  app_festival
endef

define Package/asterisk16-send-app
$(call Package/asterisk16/Default)
  TITLE:=Misc tone sending applications
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-send-app/description
$(call Package/asterisk16/Default/description)
Misc tone sending applications
  app_flash Send a flash
  app_senddtmf Send dtmf
  app_milliwatt
  app_morsecode
  app_zapateller Generate tone to block telemarketers
endef

define Package/asterisk16-followme
$(call Package/asterisk16/Default)
  TITLE:=Followme - Call forwarding
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-followme/description
$(call Package/asterisk16/Default/description)
Followme - Call forwarding
  app_followme
endef


define Package/asterisk16-queues
$(call Package/asterisk16/Default)
  TITLE:=Call queues
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-queues/description
$(call Package/asterisk16/Default/description)
Call queues
  app_queue
endef

define Package/asterisk16-record
$(call Package/asterisk16/Default)
  TITLE:=Call recording
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-record/description
$(call Package/asterisk16/Default/description)
Call recording
  app_record
  app_mixmonitor Records The audio on the current channel to the specified file. 
  func_audiohookinherit	Allow for inheritance of audiohooks
endef

define Package/asterisk16-privacy
$(call Package/asterisk16/Default)
  TITLE:=Call Privacy - Prompt for unknown numbers.
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-privacy/description
$(call Package/asterisk16/Default/description)
Call Privacy - Prompt for unknown numbers.
  app_privacy Prompt for missing calling number
endef

define Package/asterisk16-ivr-util
$(call Package/asterisk16/Default)
  TITLE:=Utilities for creating IVR
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-ivr-util/description
$(call Package/asterisk16/Default/description)
Utilities for creating IVR
  app_read Read a DTMF response
  app_authenticate Authenticate a user
  app_externalivr IVR Using an External process.
  app_disa Directed Inward Sysytem Access - Allow access to your internal dialplan with password
  app_playtones Play indication tones.
endef


define Package/asterisk16-callerid
$(call Package/asterisk16/Default)
  TITLE:=Callerid related functions.
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-callerid/description
$(call Package/asterisk16/Default/description)
Callerid related functions.
  app_setcallerid
  func_callerid
  func_blacklist
endef

define Package/asterisk16-speech
$(call Package/asterisk16/Default)
  TITLE:=Interface to Speech recognition programs
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-speech/description
$(call Package/asterisk16/Default/description)
Interface to Speech recognition programs
  app_speech_utils
  res_speech
endef

define Package/asterisk16-detect
$(call Package/asterisk16/Default)
  TITLE:=Detect coditions
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-detect/description
$(call Package/asterisk16/Default/description)
Detect coditions
  app_amd Answer machine detect
  app_talkdetect
  app_waitforring
  app_waitforsilence
endef

define Package/asterisk16-controlflow
$(call Package/asterisk16/Default)
  TITLE:=Advanced Control Flow
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-controlflow/description
$(call Package/asterisk16/Default/description)
Advanced Control Flow
  app_while
  app_macro Dialplan Macros
  app_stack Stack routines (Gosub, Return)
  app_waituntil Sleep until given epoch
  func_lock Dialplan mutexes.

endef

define Package/asterisk16-bridgeutils
$(call Package/asterisk16/Default)
  TITLE:=Bridging/originate utilities
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-bridgeutils/description
Bridging related functions
  app_originate Originate application.
  chan_bridge    Bridge Interaction Channel.
  app_confbridge
  bridge_builtin_features  Built in bridging features.
  bridge_multiplexed
  bridge_simple  Simple two channel bridging module
  bridge_softmix
endef

define Package/asterisk16-filters
$(call Package/asterisk16/Default)
  TITLE:=Volume and quality filters
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-filters/description
Filters for Asterisk
  func_speex  Noise reduction and automatic gain control (AGC).
  func_volume  Technology independent volume control.
endef

define Package/asterisk16-dialgroup
$(call Package/asterisk16/Default)
  TITLE:=Dial a group
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-dialgroup/description
Asterisk group dialing functions
  func_dialgroup  Dial a group without full queue system
endef

define Package/asterisk16-device-state
$(call Package/asterisk16/Default)
  TITLE:=Get state of devices/extensions for Asterisk.
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-device-state/description
Get state of devices/extensions for Asterisk.
 func_devstate  Get at the state of devices for manually controlled blinky lights
 func_extstate  Get the state of a hinted extension for dialplan control.  	
endef

define Package/asterisk16-res-phoneprov
$(call Package/asterisk16/Default)
  TITLE:=Provide Phone provisioning server for asterisk
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-res-phoneprov/description
Provide Phone provisioning server for asterisk
  res_phoneprov	Phone provisioning application for the asterisk internal http server
endef

define Package/asterisk16-res-limits
$(call Package/asterisk16/Default)
  TITLE:=Resource limits for Asterisk
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-res-limits/description
Provide Resource limits for Asterisk
endef

define Package/asterisk16-systemstate
$(call Package/asterisk16/Default)
  TITLE:=Get System state information for Asterisk
  DEPENDS:= +asterisk16-core
endef

define Package/asterisk16-systemstate/description
Asterisk state information for Asterisk
  app_readexten  Trivial application to read an extension into a variable.
  func_module  	Simple module check function.
  func_dialplan  Dialplan group functions check if a dialplan entry exists.
  func_config  	A function to retrieve variables from an Asterisk configuration file. 
  func_sysinfo  SYSINFO function to return various system data.
  func_version  Return the current Version strings.
endef

define Package/asterisk16-curl
$(call Package/asterisk16/Default)
  TITLE:=CURL support
  DEPENDS:= +asterisk16 +libcurl
endef

define Package/asterisk16-curl/description
$(call Package/asterisk16/Default/description)
 This package provides CURL
 support to Asterisk.
endef

CONFIGURE_ARGS+= \
	--without-curses \
	--with-gsm="$(STAGING_DIR)/usr" \
	--without-imap \
	--without-isdnnet \
	--without-kde \
	--without-misdn \
	--without-nbs \
	--with-ncurses="$(STAGING_DIR)/usr" \
	--without-netsnmp \
	--without-newt \
	--without-odbc \
	--without-ogg \
	--without-osptk \
	--with-popt="$(STAGING_DIR)/usr" \
	--without-pri \
	--without-qt \
	--without-radius \
	--without-spandsp \
	--without-suppserv \
	--without-tds \
	--without-termcap \
	--without-tinfo \
	--without-vorbis \
	--without-vpb \
	--without-sdl \
	--without-SDL_image \
	--without-x11 \
	--with-z="$(STAGING_DIR)/usr" \


EXTRA_CFLAGS:= $(TARGET_CPPFLAGS)
EXTRA_LDFLAGS:= $(TARGET_LDFLAGS)

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-app-meetme),)
  CONFIGURE_ARGS+= \
	--with-tonezone="$(STAGING_DIR)/usr" --with-dahdi="$(STAGING_DIR)/usr"
else
  CONFIGURE_ARGS+= \
	--without-tonezone --without-dahdi
endif


ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-chan-alsa),)
  CONFIGURE_ARGS+= \
        --with-asound="$(STAGING_DIR)/usr"
else
  CONFIGURE_ARGS+= \
        --without-asound
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-chan-gtalk),)
  CONFIGURE_ARGS+= \
	--with-gnutls="$(STAGING_DIR)/usr" \
	--with-iksemel="$(STAGING_DIR)/usr"
  SITE_VARS+= \
	ac_cv_lib_iksemel_iks_start_sasl=yes \
	ac_cv_lib_gnutls_gnutls_bye=yes
else
  CONFIGURE_ARGS+= \
	--without-gnutls \
	--without-iksemel
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-curl),)
  CONFIGURE_ARGS+= \
	--with-curl="$(STAGING_DIR)/usr"
else
  CONFIGURE_ARGS+= \
	--without-curl
endif

CONFIGURE_ARGS+= \
	--without-curses \
	--with-gsm=internal \
	--without-gtk \
	--without-gtk2 \
	--without-isdnnet \
	--without-kde \
	--without-misdn \
	--without-nbs \
	--with-ncurses="$(STAGING_DIR)/usr" \
	--without-netsnmp \
	--without-newt \
	--without-odbc \
	--without-ogg \
	--without-osptk \
	--with-popt="$(STAGING_DIR)/usr" \
	--without-pri \
	--without-qt \
	--without-radius \
	--without-sdl \
	--without-spandsp \
	--without-suppserv \
	--without-tds \
	--without-termcap \
	--without-tinfo \
	--without-vorbis \
	--without-vpb \
	--with-z="$(STAGING_DIR)/usr" \
	--disable-xmldoc

EXTRA_CFLAGS+= $(TARGET_CPPFLAGS)
EXTRA_LDFLAGS+= $(TARGET_LDFLAGS)

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-chan-oss),)
  CONFIGURE_ARGS+= \
        --with-oss
else
  CONFIGURE_ARGS+= \
        --without-oss
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-chan-h323),)
  CONFIGURE_ARGS+= \
	--with-h323="$(BUILD_DIR)/openh323" \
	--with-pwlib="$(BUILD_DIR)/pwlib"
  CONFIGURE_VARS+= \
	LIBS="$$$$LIBS -luClibc++ -ldl -lpthread"

  define Build/Compile/chan-h323
	$(MAKE) -C "$(PKG_BUILD_DIR)/channels/h323" \
		$(TARGET_CONFIGURE_OPTS) \
		CXXLIBS="-nodefaultlibs -luClibc++" \
		optnoshared
  endef
else
  CONFIGURE_ARGS+= \
	--without-h323 \
	--without-pwlib
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-codec-speex),)
  CONFIGURE_ARGS+= \
	--with-speex="$(STAGING_DIR)/usr"
  SITE_VARS+= \
	ac_cv_lib_speex_speex_encode=yes
  EXTRA_CFLAGS+= -I$(STAGING_DIR)/usr/include/speex
else
  CONFIGURE_ARGS+= \
	--without-speex
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-res-crypto),)
  CONFIGURE_ARGS+= \
	--with-ssl="$(STAGING_DIR)/usr"
else
  CONFIGURE_ARGS+= \
	--without-ssl
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-pgsql),)
  CONFIGURE_ARGS+= \
	--with-postgres="$(STAGING_DIR)/usr"
else
  CONFIGURE_ARGS+= \
	--without-postgres
endif

ifneq ($(SDK)$(CONFIG_PACKAGE_asterisk16-sqlite),)
  CONFIGURE_ARGS+= \
	--with-sqlite="$(STAGING_DIR)/usr"
else
  CONFIGURE_ARGS+= \
	--without-sqlite
endif


define Build/Configure
	-rm $(PKG_BUILD_DIR)/menuselect.makeopts
	( cd $(PKG_BUILD_DIR); ./bootstrap.sh )
	$(call Build/Configure/Default,,$(SITE_VARS))
endef

define Build/Compile
	$(MAKE) -C "$(PKG_BUILD_DIR)" \
		include/asterisk/version.h \
		include/asterisk/buildopts.h defaults.h \
		makeopts.embed_rules
	ASTCFLAGS="$(EXTRA_CFLAGS) -DLOW_MEMORY $(TARGET_CFLAGS)" \
	ASTLDFLAGS="$(EXTRA_LDFLAGS)" \
	$(MAKE) -C "$(PKG_BUILD_DIR)" \
		ASTVARLIBDIR="/usr/lib/asterisk" \
		NOISY_BUILD="1" \
		DEBUG="" \
		OPTIMIZE="" \
		DESTDIR="$(PKG_INSTALL_DIR)" \
		LDOPTS="-L$(BUILD_DIR)/openh323/lib -ldl -lpthread" \
		all install samples
	$(SED) 's|/var/lib/asterisk|/usr/lib/asterisk|g' $(PKG_INSTALL_DIR)/etc/asterisk/musiconhold.conf

	$(TARGET_CC) -O2 $(PKG_BUILD_DIR)/contrib/utils/rawplayer.c -o $(PKG_BUILD_DIR)/rawplayer
endef


define Build/InstallDev
	mkdir -p $(1)/usr/include/asterisk/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/asterisk/*.h $(1)/usr/include/asterisk/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/asterisk.h $(1)/usr/include/
endef

define Package/asterisk16-core/conffiles
/etc/asterisk/asterisk.conf
/etc/asterisk/codecs.conf
/etc/asterisk/dnsmgr.conf
/etc/asterisk/extconfig.conf
/etc/asterisk/extensions.conf
/etc/asterisk/http.conf
/etc/asterisk/indications.conf
/etc/asterisk/indications.conf
/etc/asterisk/logger.conf
/etc/asterisk/manager.conf
/etc/asterisk/modules.conf
/etc/asterisk/say.conf
/etc/asterisk/sla.conf
/etc/asterisk/users.conf
endef

define Package/asterisk16-core/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	for f in asterisk extensions features codecs dnsmgr extconfig http say sla users \
		indications logger manager modules \
		sip sip_notify rtp; do \
		$(CP) $(PKG_INSTALL_DIR)/etc/asterisk/$$$$f.conf $(1)/etc/asterisk/ ; \
	done
	$(INSTALL_DATA) ./files/modules.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/keys
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in codec_gsm format_gsm pbx_config res_indications app_dial chan_local ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/moh
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/asterisk $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/safe_asterisk $(1)/usr/sbin/
	$(INSTALL_DIR) $(1)/etc/default
	$(INSTALL_DATA)  ./files/asterisk.default $(1)/etc/default/asterisk
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN)  ./files/asterisk.init $(1)/etc/init.d/asterisk
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/uci
	$(CP) ./files/uci/* $1/usr/lib/asterisk/uci
	$(INSTALL_DIR) $(1)/etc/asterisk/macros
	$(CP) ./files/macros/* $1/etc/asterisk/macros
endef

define Package/asterisk16-core/postinst
#!/bin/sh
if [ -z "${IPKG_INSTROOT}" ] ; then
  ROOT=/
else
  ROOT=`echo $${PKG_ROOT} | sed 's:[\/]:\\\&:g' -`
fi
/bin/sed -i 's/\ \/etc/\ '$${ROOT}'etc/g' $${PKG_ROOT}/etc/asterisk/asterisk.conf
/bin/sed -i 's/\ \/var\/spool/\ '$${ROOT}'var\/spool/g' $${PKG_ROOT}/etc/asterisk/asterisk.conf
/bin/sed -i 's/\ \/var\/log/\ '$${ROOT}'var\/log/g' $${PKG_ROOT}/etc/asterisk/asterisk.conf
/bin/sed -i 's/\ \/usr/\ '$${ROOT}'usr/g' $${PKG_ROOT}/etc/asterisk/asterisk.conf
/bin/sed -i 's/^DEST=/DEST='$${ROOT}'/g' $${PKG_ROOT}/etc/init.d/asterisk
/bin/sed -i 's/OPTIONS=\"\"/OPTIONS=\"-C\ '$${ROOT}'etc\/asterisk\/asterisk.conf\"/g' $${PKG_ROOT}/etc/default/asterisk
mkdir -p $${PKG_ROOT}/etc/asterisk/conf.d
cd $${PKG_ROOT}/etc/asterisk/conf.d
ln -s ../../../usr/lib/asterisk/uci/voicemailconf 10-voicemail
ln -s ../../../usr/lib/asterisk/uci/mohconf       15-moh
ln -s ../../../usr/lib/asterisk/uci/featureconf   20-features
ln -s ../../../usr/lib/asterisk/uci/lastcall      25-lastcall
ln -s ../../../usr/lib/asterisk/uci/meetmeconf    30-meetme
ln -s ../../../usr/lib/asterisk/uci/sipiaxconf    35-sipiax
ln -s ../../../usr/lib/asterisk/uci/talkclock     40-talkclock
ln -s ../../../usr/lib/asterisk/uci/voicemenu     45-voicemenu
ln -s ../../../usr/lib/asterisk/uci/disaconf      50-disaconf
ln -s ../../../usr/lib/asterisk/uci/queueconf     55-queuconf
endef

define Package/asterisk16/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk
endef

define Package/asterisk16-mini/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk
endef

define Package/asterisk16-app-meetme/conffiles
/etc/asterisk/meetme.conf
endef

define Package/asterisk16-app-meetme/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/meetme.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_meetme app_page ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/conf-* $(1)/usr/lib/asterisk/sounds/
endef


define Package/asterisk16-chan-oss/conffiles
/etc/asterisk/oss.conf
endef

define Package/asterisk16-chan-oss/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/oss.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_oss.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-app-meetme/conffiles
/etc/asterisk/meetme.conf
endef

define Package/asterisk16-app-meetme/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/meetme.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_meetme.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-chan-oss/conffiles
/etc/asterisk/oss.conf
endef

define Package/asterisk16-chan-oss/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/oss.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_oss.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-chan-alsa/conffiles
/etc/asterisk/alsa.conf
endef

define Package/asterisk16-chan-alsa/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/alsa.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_alsa.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-chan-gtalk/conffiles
/etc/asterisk/gtalk.conf
/etc/asterisk/jabber.conf
endef

define Package/asterisk16-chan-gtalk/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/gtalk.conf $(1)/etc/asterisk/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/jabber.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_gtalk.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/res_jabber.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-chan-h323/conffiles
/etc/asterisk/h323.conf
endef

define Package/asterisk16-chan-h323/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/h323.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_h323.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-chan-mgcp/install
/etc/asterisk/mgcp.conf
endef

define Package/asterisk16-chan-mgcp/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/mgcp.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_mgcp.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-chan-skinny/conffiles
/etc/asterisk/skinny.conf
endef

define Package/asterisk16-chan-skinny/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/skinny.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_skinny.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-chan-jingle/conffiles
/etc/asterisk/jingle.conf
endef

define Package/asterisk16-chan-jingle/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/jingle.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_jingle.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-chan-unistim/conffiles
/etc/asterisk/unistim.conf
endef

define Package/asterisk16-chan-unistim/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/unistim.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_unistim.so $(1)/usr/lib/asterisk/modules/
endef


#define Package/asterisk16-codec-ilbc/install
#	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
#	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/codec_ilbc.so $(1)/usr/lib/asterisk/modules/
#	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/format_ilbc.so $(1)/usr/lib/asterisk/modules/
#endef


define Package/asterisk16-codec-lpc10/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/codec_lpc10.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-codec-speex/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/codec_speex.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-pbx-dundi/conffiles
/etc/asterisk/dundi.conf
endef

define Package/asterisk16-pbx-dundi/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/dundi.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/pbx_dundi.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-res-agi/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/agi-bin
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/res_agi.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-res-crypto/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in res_crypto func_aes ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef


define Package/asterisk16-pgsql/conffiles
/etc/asterisk/cdr_pgsql.conf
/etc/asterisk/res_pgsql.conf
endef

define Package/asterisk16-pgsql/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	install -m0600 $(PKG_INSTALL_DIR)/etc/asterisk/cdr_pgsql.conf $(1)/etc/asterisk/
	install -m0600 $(PKG_INSTALL_DIR)/etc/asterisk/res_pgsql.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/cdr_pgsql.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/res_config_pgsql.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-sqlite/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in cdr_sqlite3_custom cdr_sqlite res_config_sqlite ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-sounds/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/* $(1)/usr/lib/asterisk/sounds/en/
	rm -f $(1)/usr/lib/asterisk/sounds/en/vm-*
	rm -f $(1)/usr/lib/asterisk/sounds/en/x
	rm -f $(1)/usr/lib/asterisk/sounds/en/dir-*
	rm -f $(1)/usr/lib/asterisk/sounds/en/dictate/*
	rm -f $(1)/usr/lib/asterisk/sounds/en/followme/*
	rm -f $(1)/usr/lib/asterisk/sounds/en/conf-*
	rm -f $(1)/usr/lib/asterisk/sounds/en/queue-*
	rm -f $(1)/usr/lib/asterisk/sounds/en/priv*
	rm -f $(1)/usr/lib/asterisk/sounds/en/auth-*
	rm -f $(1)/usr/lib/asterisk/sounds/en/agent-*
	rm -f $(1)/usr/lib/asterisk/sounds/en/tt-*
	rm -f $(1)/usr/lib/asterisk/sounds/en/demo-*
endef

define Package/asterisk16-voicemail-support/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_hasnewvoicemail func_vmcount ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-voicemail-mini/conffiles
/etc/asterisk/minivm.conf
endef

define Package/asterisk16-voicemail-mini/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/minivm.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_minivm.so $(1)/usr/lib/asterisk/modules/
endef


define Package/asterisk16-voicemail/conffiles
/etc/asterisk/voicemail.conf
endef

define Package/asterisk16-voicemail/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/voicemail.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_voicemail.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-voicemail-sounds-en/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/vm-*.gsm $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-rawplayer/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN)	$(PKG_BUILD_DIR)/rawplayer \
			$(1)/usr/bin
endef

define Package/asterisk16-agents/conffiles
/etc/asterisk/agents.conf
endef

define Package/asterisk16-agents/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/agents.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_agent.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/agent-* $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-iax/conffiles
/etc/asterisk/iax.conf
/etc/asterisk/iaxprov.conf
endef

define Package/asterisk16-iax/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	for f in iax.conf iaxprov.conf ; do \
	  $(CP) $(PKG_INSTALL_DIR)/etc/asterisk/$$$$f $(1)/etc/asterisk/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_iax2.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-sip/conffiles
/etc/asterisk/sip.conf
/etc/asterisk/sip_notify.conf
/etc/asterisk/rtp.conf
/etc/asterisk/udptl.conf
endef

define Package/asterisk16-sip/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	for f in sip.conf sip_notify.conf rtp.conf udptl.conf ; do \
	  $(CP) $(PKG_INSTALL_DIR)/etc/asterisk/$$$$f $(1)/etc/asterisk/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/chan_sip.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-codec-wav/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in codec_adpcm format_pcm format_wav_gsm format_wav ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-codec-ualaw/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in codec_alaw codec_a_mu codec_ulaw ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-format-misc/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in format_sln format_sln16 format_vox format_ilbc format_siren14 format_siren7 ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-format-licensed/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in format_g726 format_g723 format_g729 ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-codec-g726/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/codec_g726.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-codec-g722/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/codec_g722.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-format-video/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in format_h263 format_h264 ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-variables/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_db func_global func_env func_timeout ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-enum/conffiles
/etc/asterisk/enum.conf
endef

define Package/asterisk16-enum/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/enum.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/func_enum.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-basic/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_logic func_math func_strings func_rand func_cut func_sprintf ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-encode/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_base64 func_md5 func_sha1 func_uri ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-realtime/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_realtime pbx_realtime res_realtime ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-ael/conffiles
/etc/asterisk/extensions.ael
endef

define Package/asterisk16-ael/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/extensions.ael $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in res_ael_share pbx_ael ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/aelparse $(1)/usr/sbin/
endef

define Package/asterisk16-adsi/conffiles
/etc/asterisk/adsi.conf
endef

define Package/asterisk16-adsi/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/adsi.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in res_adsi app_adsiprog ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-features/conffiles
/etc/asterisk/features.conf
endef

define Package/asterisk16-features/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/features.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in res_features app_transfer app_parkandannounce res_monitor ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-moh/conffiles
/etc/asterisk/musiconhold.conf
endef

define Package/asterisk16-moh/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/musiconhold.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in res_musiconhold ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/streamplayer $(1)/usr/sbin/
endef

define Package/asterisk16-smdi/conffiles
/etc/asterisk/smdi.conf
endef

define Package/asterisk16-smdi/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/smdi.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/res_smdi.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-sounds-tt/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/tt-* $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-sounds-demo/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/demo-* $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-linejack/conffiles
/etc/asterisk/phone.conf
endef

define Package/asterisk16-linejack/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/phone.conf $(1)/etc/asterisk/
endef

define Package/asterisk16-app-misc/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_random app_sayunixtime app_sendtext app_url app_readfile app_system app_exec func_shell ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-image/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_image format_jpeg ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-sms/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_sms.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/smsq $(1)/usr/sbin/
endef

define Package/asterisk16-icecast/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_ices.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-mp3/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_mp3.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-cli/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_userevent res_clioriginate res_convert res_clialiases ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

#define Package/asterisk16-isdn/install
#	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
#	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_settransfercapability.so $(1)/usr/lib/asterisk/modules/
#endef
#
define Package/asterisk16-deprecated/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_db.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-groups/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/func_groupcount.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-spool/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/pbx_spool.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-nbs/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_nbscat.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-alarmreceiver/conffiles
/etc/asterisk/alarmreceiver.conf
endef

define Package/asterisk16-alarmreceiver/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/alarmreceiver.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_alarmreceiver.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-cdr/conffiles
/etc/asterisk/cdr.conf
/etc/asterisk/cdr_custom.conf
/etc/asterisk/cdr_manager.conf
endef

define Package/asterisk16-cdr/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	for f in cdr.conf cdr_custom.conf cdr_manager.conf ; do \
	  $(CP) $(PKG_INSTALL_DIR)/etc/asterisk/$$$$f $(1)/etc/asterisk/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_cdr app_forkcdr app_setcdruserfield cdr_csv cdr_custom cdr_manager func_cdr ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-channel/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_chanisavail app_channelredirect app_chanspy func_channel app_softhangup app_directed_pickup ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-debug/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_echo pbx_loopback app_dumpchan app_verbose app_test ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-menu-misc/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_playback app_controlplayback app_directory app_dictate ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	for f in dir-* dictate/* ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/$$$$f $(1)/usr/lib/asterisk/sounds/en/ ; \
	done
endef

define Package/asterisk16-festival/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_festival.so $(1)/usr/lib/asterisk/modules/
endef

define Package/asterisk16-send-app/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_flash app_senddtmf app_milliwatt app_morsecode app_zapateller ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-followme/conffiles
/etc/asterisk/followme.conf
endef

define Package/asterisk16-followme/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/followme.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_followme.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/followme/* $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-queues/conffiles
/etc/asterisk/queuerules.conf
/etc/asterisk/queues.conf
endef

define Package/asterisk16-queues/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/queues.conf $(1)/etc/asterisk/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/queuerules.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_queue.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/queue-* $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-record/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_record app_mixmonitor func_audiohookinherit ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

#define Package/asterisk16-privacy/conffiles
#/etc/asterisk/privacy.conf
#endef
#	$(INSTALL_DIR) $(1)/etc/asterisk
#	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/privacy.conf $(1)/etc/asterisk/

define Package/asterisk16-privacy/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/app_privacy.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/priv* $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-ivr-util/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_read app_authenticate app_externalivr app_disa app_playtones ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/sounds/en
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/sounds/en/auth-* $(1)/usr/lib/asterisk/sounds/en/
endef

define Package/asterisk16-callerid/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_setcallerid func_callerid func_blacklist ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-speech/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_speech_utils res_speech ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-detect/conffiles
/etc/asterisk/amd.conf
endef

define Package/asterisk16-detect/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/amd.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_amd app_talkdetect app_waitforring app_waitforsilence ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-controlflow/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_while app_macro app_stack app_waituntil func_lock ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-curl/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/func_curl.so $(1)/usr/lib/asterisk/modules/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/res_curl.so $(1)/usr/lib/asterisk/modules/
endef

define BuildAsterisk16ModuleTemplate

  define Package/asterisk16-$(subst _,-,$(1))
  $$(call Package/asterisk16/Default)
    TITLE:=$(2) support
    DEPENDS:= +asterisk16
  endef

  define Package/asterisk16-$(subst _,-,$(1))/description
  $$(call Package/asterisk16/Default/description)
    This package provides support $(3) in Asterisk.
  endef

  define Package/asterisk16-$(subst _,-,$(1))/install
	$(INSTALL_DIR) $$(1)/usr/lib/asterisk/modules
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$(1).so $$(1)/usr/lib/asterisk/modules/
  endef

  $$(eval $$(call BuildPackage,asterisk16-$(subst _,-,$(1))))
endef

define Package/asterisk16-dahdi/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in chan_dahdi app_dahdibarge app_dahdiscan codec_dahdi app_getcpeid app_dahdiras ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
	$(INSTALL_DIR) $(1)/usr/lib/asterisk
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/firmware $(1)/usr/lib/asterisk/
endef

define Package/asterisk16-bridgeutils/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_originate chan_bridge app_confbridge bridge_builtin_features bridge_multiplexed bridge_simple bridge_softmix ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-filters/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_speex func_volume ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-dialgroup/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_dialgroup ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef


define Package/asterisk16-device-state/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_devstate func_extstate ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-phoneprov/conffiles
/etc/asterisk/phoneprov.conf
endef

define Package/asterisk16-res-phoneprov/install
	$(INSTALL_DIR) $(1)/etc/asterisk
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/asterisk/phoneprov.conf $(1)/etc/asterisk/
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in func_devstate res_phoneprov ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-res-limits/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in res_limit ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

define Package/asterisk16-systemstate/install
	$(INSTALL_DIR) $(1)/usr/lib/asterisk/modules
	for f in app_readexten func_module func_dialplan func_config func_sysinfo func_version ; do \
	  $(CP) $(PKG_INSTALL_DIR)/usr/lib/asterisk/modules/$$$$f.so $(1)/usr/lib/asterisk/modules/ ; \
	done
endef

$(eval $(call BuildPackage,asterisk16-core))
$(eval $(call BuildPackage,asterisk16))
$(eval $(call BuildPackage,asterisk16-mini))
$(eval $(call BuildPackage,asterisk16-app-meetme))
$(eval $(call BuildPackage,asterisk16-chan-oss))
$(eval $(call BuildPackage,asterisk16-chan-alsa))
$(eval $(call BuildPackage,asterisk16-chan-gtalk))
$(eval $(call BuildPackage,asterisk16-chan-h323))
$(eval $(call BuildPackage,asterisk16-chan-mgcp))
$(eval $(call BuildPackage,asterisk16-chan-skinny))
$(eval $(call BuildPackage,asterisk16-chan-jingle))
$(eval $(call BuildPackage,asterisk16-chan-unistim))
#$(eval $(call BuildPackage,asterisk16-codec-ilbc))
$(eval $(call BuildPackage,asterisk16-codec-lpc10))
$(eval $(call BuildPackage,asterisk16-codec-speex))
$(eval $(call BuildPackage,asterisk16-pbx-dundi))
$(eval $(call BuildPackage,asterisk16-res-agi))
$(eval $(call BuildPackage,asterisk16-res-crypto))
$(eval $(call BuildPackage,asterisk16-pgsql))
$(eval $(call BuildPackage,asterisk16-sqlite))
$(eval $(call BuildPackage,asterisk16-voicemail))
$(eval $(call BuildPackage,asterisk16-voicemail-support))
$(eval $(call BuildPackage,asterisk16-voicemail-sounds-en))
$(eval $(call BuildPackage,asterisk16-sounds))
$(eval $(call BuildPackage,asterisk16-rawplayer))
$(eval $(call BuildPackage,asterisk16-agents))
$(eval $(call BuildPackage,asterisk16-iax))
$(eval $(call BuildPackage,asterisk16-sip))
$(eval $(call BuildPackage,asterisk16-codec-wav))
$(eval $(call BuildPackage,asterisk16-codec-ualaw))
$(eval $(call BuildPackage,asterisk16-format-misc))
$(eval $(call BuildPackage,asterisk16-format-licensed))
$(eval $(call BuildPackage,asterisk16-codec-g726))
$(eval $(call BuildPackage,asterisk16-codec-g722))
$(eval $(call BuildPackage,asterisk16-format-video))
$(eval $(call BuildPackage,asterisk16-variables))
$(eval $(call BuildPackage,asterisk16-enum))
$(eval $(call BuildPackage,asterisk16-basic))
$(eval $(call BuildPackage,asterisk16-encode))
$(eval $(call BuildPackage,asterisk16-realtime))
$(eval $(call BuildPackage,asterisk16-ael))
$(eval $(call BuildPackage,asterisk16-adsi))
$(eval $(call BuildPackage,asterisk16-features))
$(eval $(call BuildPackage,asterisk16-moh))
$(eval $(call BuildPackage,asterisk16-smdi))
$(eval $(call BuildPackage,asterisk16-sounds-tt))
$(eval $(call BuildPackage,asterisk16-sounds-demo))
$(eval $(call BuildPackage,asterisk16-linejack))
$(eval $(call BuildPackage,asterisk16-app-misc))
$(eval $(call BuildPackage,asterisk16-image))
$(eval $(call BuildPackage,asterisk16-sms))
$(eval $(call BuildPackage,asterisk16-icecast))
$(eval $(call BuildPackage,asterisk16-mp3))
$(eval $(call BuildPackage,asterisk16-cli))
#$(eval $(call BuildPackage,asterisk16-isdn))
$(eval $(call BuildPackage,asterisk16-deprecated))
$(eval $(call BuildPackage,asterisk16-groups))
$(eval $(call BuildPackage,asterisk16-spool))
$(eval $(call BuildPackage,asterisk16-nbs))
$(eval $(call BuildPackage,asterisk16-alarmreceiver))
$(eval $(call BuildPackage,asterisk16-cdr))
$(eval $(call BuildPackage,asterisk16-channel))
$(eval $(call BuildPackage,asterisk16-debug))
$(eval $(call BuildPackage,asterisk16-menu-misc))
$(eval $(call BuildPackage,asterisk16-festival))
$(eval $(call BuildPackage,asterisk16-send-app))
$(eval $(call BuildPackage,asterisk16-followme))
$(eval $(call BuildPackage,asterisk16-queues))
$(eval $(call BuildPackage,asterisk16-record))
$(eval $(call BuildPackage,asterisk16-privacy))
$(eval $(call BuildPackage,asterisk16-ivr-util))
$(eval $(call BuildPackage,asterisk16-callerid))
$(eval $(call BuildPackage,asterisk16-speech))
$(eval $(call BuildPackage,asterisk16-detect))
$(eval $(call BuildPackage,asterisk16-controlflow))
$(eval $(call BuildPackage,asterisk16-bridgeutils))
$(eval $(call BuildPackage,asterisk16-filters))
$(eval $(call BuildPackage,asterisk16-dialgroup))
$(eval $(call BuildPackage,asterisk16-device-state))
$(eval $(call BuildPackage,asterisk16-res-phoneprov))
$(eval $(call BuildPackage,asterisk16-res-limits))
$(eval $(call BuildPackage,asterisk16-systemstate))
$(eval $(call BuildPackage,asterisk16-curl))

#$(eval $(call BuildAsterisk16ModuleTemplate,app_authenticate,Authenticate,support for executing arbitrary authenticate commands))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_chanisavail,Channel availability check,support for checking if a channel is available))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_chanspy,Channel listen in,support for listening in on any channel))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_directed_pickup,Directed call pickup,support for directed call pickup))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_exec,Exec application,support for application execution))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_minivm,Minimal voicemail system,a voicemail system in small building blocks working together based on the Comedian Mail voicemail system))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_readexten,Extension to variable,a trivial application to read an extension into a variable))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_read,Variable read,a trivial application to read a variable))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_sayunixtime,Say Unix time,an application to say Unix time))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_sms,SMS,SMS support (ETSI ES 201 912 protocol 1)))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_stack,Stack applications, stack applications Gosub Return etc.))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_system,System exec,support for executing system commands))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_talkdetect,File playback with audio detect,for file playback with audio detect))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_waituntil,Sleep,support sleeping until the given epoch))
#$(eval $(call BuildAsterisk16ModuleTemplate,app_while,While loop,a while loop implementation))
#$(eval $(call BuildAsterisk16ModuleTemplate,chan_agent,Agents proxy channel, an implementation of agents proxy channel))
#$(eval $(call BuildAsterisk16ModuleTemplate,chan_local,Local proxy channel, an implementation of local proxy channel))
#$(eval $(call BuildAsterisk16ModuleTemplate,codec_ulaw,Signed linear to ulaw translation,translation between signed linear and ulaw codecs))
#$(eval $(call BuildAsterisk16ModuleTemplate,codec_a_mu,Alaw to ulaw translation,translation between alaw and ulaw codecs))
#$(eval $(call BuildAsterisk16ModuleTemplate,codec_g726,Signed linear to G.726 translation,translation between signed linear and ITU G.726-32kbps codecs))
#$(eval $(call BuildAsterisk16ModuleTemplate,format_g726,G.726,support for headerless G.726 16/24/32/40kbps data format))
#$(eval $(call BuildAsterisk16ModuleTemplate,format_g729,G.729,support for raw headerless G729 data))
#$(eval $(call BuildAsterisk16ModuleTemplate,format_sln,Raw slinear format,support for raw slinear format))
#$(eval $(call BuildAsterisk16ModuleTemplate,format_sln16,Raw slinear 16 format,support for Raw slinear 16 format))
#$(eval $(call BuildAsterisk16ModuleTemplate,func_db,Database interaction,functions for interaction with the database))
#$(eval $(call BuildAsterisk16ModuleTemplate,func_devstate,Blinky lights control,functions for manually controlled blinky lights))
#$(eval $(call BuildAsterisk16ModuleTemplate,func_vmcount,vmcount dialplan,a vmcount dialplan function))
#$(eval $(call BuildAsterisk16ModuleTemplate,func_extstate,Hinted extension state,retrieving the state of a hinted extension for dialplan control))
#$(eval $(call BuildAsterisk16ModuleTemplate,func_global,Global variable,global variable dialplan functions))
#$(eval $(call BuildAsterisk16ModuleTemplate,func_shell,Shell,support for shell execution))
#$(eval $(call BuildAsterisk16ModuleTemplate,pbx_ael,Asterisk Extension Logic,support for symbolic Asterisk Extension Logic))
#$(eval $(call BuildAsterisk16ModuleTemplate,res_ael_share,Shareable AEL code,support for shareable AEL code mainly between internal and external modules))
#$(eval $(call BuildAsterisk16ModuleTemplate,pbx_spool,Call Spool,outgoing call spool support))
#$(eval $(call BuildAsterisk16ModuleTemplate,res_agi,Asterisk Gateway Interface,support for the Asterisk Gateway Interface extension))
# $(eval $(call BuildAsterisk16ModuleTemplate,app_alarmreceiver,Alarm receiver,Central Station Alarm receiver for Ademco Contact ID))
# $(eval $(call BuildAsterisk16ModuleTemplate,app_setcallerid,Set callerid,support for setting callerid))
# $(eval $(call BuildAsterisk16ModuleTemplate,app_verbose,Verbose logging,Verbose logging application))
# $(eval $(call BuildAsterisk16ModuleTemplate,func_channel,Channel info,Channel info dialplan function))
# $(eval $(call BuildAsterisk16ModuleTemplate,func_blacklist,Blacklist on callerid,looking up the callerid number, and see if it is blacklisted))
# $(eval $(call BuildAsterisk16ModuleTemplate,app_originate,Originate a call,originating an outbound call and connecting it to a specified extension or application))

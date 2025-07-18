# Release note

This is stable releases of Mew 6.10.

## Differences between Mew 6.10 and Mew 6.9

* XOAUTH2 support. Please see Sec 9.13 of the manual.
* Use C.UTF-8 if available to display non-ASCII names for GnuPG
  programs.
  [#179](https://github.com/kazu-yamamoto/Mew/pull/179)
* Enable IPv6 support of stunnel by default.
  [#177](https://github.com/kazu-yamamoto/Mew/pull/177)
* Add GnuTLS support.
  [#175](https://github.com/kazu-yamamoto/Mew/pull/175)
* Supporting stunnel >=5.15 only.
  [#174](https://github.com/kazu-yamamoto/Mew/pull/174)
* Separately check if stunnel supports 'foreground', 'pid' and
  'syslog' options.
  [#171](https://github.com/kazu-yamamoto/Mew/pull/170)
* Use configured file names as relative paths from mew-home.
  [#170](https://github.com/kazu-yamamoto/Mew/pull/170)
* And several bug fixes.

## Differences between Mew 6.9 and Mew 6.8

* Mew now supports Emacs 26.1 or later only.
* Supporting coming Emacs 29.
* Supporting "stunnel" 5.15.
* Supporting native compilation.
* `mew-smtp-port` now supports Unix domain socket.  If it is set to an
  absolute pathname such as "/var/run/msp.sock", Mew will use it as a
  Unix domain socket.  The value of `mew-smtp-server` will be ignored.
  This feature requires `make-network-process` introduced since Emacs
  22.
* Some bug fixes.

## Differences between Mew 6.8 and Mew 6.7

* Mew now supports Emacs 24.3 or later only.
* Supporting "stunnel" 5.
* Supporting GnuPG 2.1.23 or later.
  The command name should be "gpg" instead of "gpg2".
  Put the following to your "~/.gnupg/gpg.conf".

```
no-auto-key-retrieve
auto-key-locate local
```

* Using LibreOffice (soffice) on Unix by default.

## Differences between Mew 6.7 and Mew 6.6

* Security fix for GnuPG.
* GnuPG 2.1 is supported only for master password, not for PGP/MIME
  and S/MIME.

## Differences between Mew 6.6 and Mew 6.5

* Better image supports.
* The body encoded with Base64/Quoted-Printable is decoded.
* Catching up to the latest GnuPG.
* Support of ISO-2022-JP-3 was removed in favor of UTF-8.
* The speed to move the cursor in Summary mode got much faster.
* Supporting stunnel 5.

##  Differences between Mew 6.5 and Mew 6.4

* Catching up to latest "stunnel".
* Catching up to Ruby 1.9.
* Highlighting HTML produced by "w3m".

## Differences between Mew 6.4 and Mew 6.3

* Zip support for reading and composing.
* Many bug fixes.

## Differences between Mew 6.3 and Mew 6.2

* Mew 6.3 works on Emacs 23 properly.
* Mew 6.2 does not work on Emacs 21. This bug has been fixed.

## Differences between Mew 6.2 and Mew 6.1

* Edit mode has been implemented.
* The encoding of format=flowed has been implemented.
* IMAP mark synchronization has been implemented.
* "V" (i.e "smew") became much faster. You MUST re-create the DB
  with "cmew -f".
* "k/" and "k?" can be used even while updating the DB.

## Differences between Mew 6.1 and Mew 5.2

* Configuration in ".mew.el", especially of mew-config-alist is
  simplified. See the config2 node in info.
* Virtual mode is categorized to Selection and Thread. You can create
  Selection by keyword, dialog, sorting, and so on. You can make
  Thread even of Selection as well as of Summary.
* "S" is now virtual sort creating Selection. Physical sort is
  assigned to "M-s".
* Mew now supports Emacs 21.4 or later only. Please use Emacs 22.x
  unless you have a particular reason. Mew does support Emacs 23.x.
* Punycode is supported. Mew now can display internationalized domain
  names.
* "Z" collects a folder list according to the current world.
  No numeric argument is necessary any more.
* "_" toggles a long line: normal, long, wrapped.
* You can use gmail with IMAP.
* Configuration in ".mew.el" is simplified between Mew 5.2 and Mew
  6.1.  Almost all old configuration works. However, if you are using
  complex configuration, please translate it to the new one. See the
  config2 node in info. Complex configuration includes:

    - `mew-header-alist`
    - `mew-refile-guess-alist`
    - `mew-inbox-action-alist`

## Differences between Mew 5.2 and Mew 5.1

* Full S/MIME support based on GnuPG 2.
	http://www.mew.org/feature/smime.html.en
	http://www.mew.org/feature/smime.html.ja
* Automatic resizing for large JPEG/PNG images.
* Hyper Estraier support.
	http://www.mew.org/feature/est.html.en
	http://www.mew.org/feature/est.html.ja

## Differences between Mew 5.1 and Mew 4.2

* The ".mew" suffix is introduced for OS level search mechanisms.
* OS level search mechanisms including Spotlight, Windows Desktop
  Search, Google Desktop are integrated.
* The mechanism of master password was implemented.
  Set mew-use-master-passwd to t to use it.
* When sending a message, if your SMTP server requires user
  authentication, Mew asks you to input your password. You don't have
  to configure mew-smtp-user anymore.
* In Draft mode, addresses which are not considered safe turn red.
  See mew-safe-addresses, mew-warn-addresses, mew-safe-domains, and
  mew-warn-domains.
* You can securely save your passwords to a file with a master
  password.
* "li" copies a message to an IMAP folder.
* "I" now works in Thread mode.
* "C-cC-e" in Summary has been drastically improved.
* "C-cC-t" and "C-cC-y" in Summary were obsoleted.
* 'mew-inbox-action-alist' can be set in 'mew-config-alist'.
* "v" in Summary mode displays line numbers when off.
* "C-uj" in Summary mode jumps to the message whose message number is
  specified.
* "C-uB" decomposes any attached files.
* If you want to put the 'D' mark to duplicated messages
  whose bodies are identical (ie spams), set 
  mew-summary-form-mark-spam to t.
* All variables can be defined in ".mew.el". You don't have to
  set specific variables in ".emacs".

## Differences between Mew 4.2 and Mew 4.1

* mew-nmz.el has been integrated. You can search messages with
  keyword DB. For more information, see info.
* "C-uw" prepares a draft whose To: is the address on From: of the
  current message.
* "e" in Summary can convert any mark to new one.
* S/MIME has been supported. (alpha stage)
* IMAP UTF-7 support. You can use non-ASCII characters for folder
  names.
* TLS has been supported.
* Fixing a bug of SSL.
* Drag and Drop composing has been supported.
* Many small bug fixes.

## Differences between Mew 4.1 and Mew 3.2

* Summary mode format
	- Parts of message bodies are displayed.
	- Message number disappeared.
	- "=" displays its message number.
	- Refile information overrides its body part in Summary mode.
	- 'mew-scan-form*' is now 'mew-summary-form*'.
	- "j" now jumps to a message with line number instead of its
	  message number.
	- You can still pack messages by "O" in a local folder.

* A new mark scheme
	- Marks are preserved even if Emacs is terminated.
	- The unread mark 'U' is introduced. 
	- The multi mark '@' is obsoleted. 
	- To handle multiple messages, use the target mark '*'. 
	- To preserve the target mark '*', use the escape mark '$'.
	- You can create Virtual mode for unread messages by
	  "C-um/" + 'U'.

* Summary mode
	- Refile information is logged. See "Mail/Refilelog".
	- You can pick or grep for a region as well as the entire
          folder. ("?" and "'")
	- You can rename and remove folders. ("Rd" and "Rr")

* Message mode

	- If To:/Cc: contains many addresses, they are covered with a
	  invisible veil except the first four lines. To toggle the
	  veil, type "zv".

* Virtual mode
	- You can pick or grep if the Virtual mode is created of
	  a one physical folder.
	- You can make a thread if the Virtual mode is created of
	  a one physical folder.

* Draft mode
	- You can complete addresses even if they have the same user
          name. See 'mew-use-full-alias'.
	- Fixing a bug of 'mew-make-message-hook' so that ispell-message
	  works.

* IMAP
	- A new name space. You can omit the unnecessary prefix,
          "inbox."!
	- Fcc: %backup
	- Invalid cache messages are marked with "#".
	- Invalid cache messages can be created even online (by "x").
	- IMAP messages are cached with the same UID number.
	- Transition mechanism from POP to IMAP is provided.
	  M-x mew-summary-from-local-to-imap copies messages on a
	  local file system to an IMAP server.

* NetNews

	- NetNews articles are now gained access by article numbers
	  instead of Message-Id:. Articles are cached with the same
	  article number.

* Spam filter
	- Mew side filtering when scanning/retrieving. 
	  See 'mew-inbox-action-alist'.
	- Mew side filtering by a command. ('"')
	- IMAP server side filtering. See 'mew-imap-spam-field'.
	- Learning as spam or ham. ("ls" and "lh")

* Network
	- POP/IMAP/SMTP/NNTP preserves its status even if its
	  connection is lost by accident.

* Other
	- "mewls" is now called "mewl" so that both "mewls" or Mew 2/3
          and "mewl" for Mew 4 co-exist.

## Differences between Mew 3.2 and Mew 3.1

* If SSL/SSH is used for message retrieval by POP/IMAP/NNTP,
  it is notified in mode line ("Sec" or a lock image).
* Supporting Emacs 21.3.50's native UTF-8.
* Translation between Latin 0 and Latin 1.
* A certificate of an SSL server can be verified. For this, "stunnel"
  v3 and v4 are supported and support for "openssl s_client" is
  obsoleted.
* Supporting X-Face: on Emacs 21. To use X-Face: on any Emacsen,
  install both the "compface" package and the "netpbm" package.
* Obsoleting the following variables:
	mew-noreplyto-to-list
	mew-noreplyto-cc-list
	mew-replyto-to-list
	mew-replyto-cc-list
	mew-fromme-to-list
	mew-fromme-cc-list
  And defining the following variables:
	mew-reply-all-alist
	mew-reply-sender-alist
	mew-reply-fromme-alist
  This change enables support for NetNews and non-standard fields
  such as Mail-Folloup-To:.
* New commands in Summary mode.
	"\", "M-\", "m/"
* Many bug fixes.

## Differences between Mew 3.1 and Mew 2.2

* Supporting Darwin.
* The structure of folder list is changed. Type "1Z" once after
  upgrading to Mew 3.1
* You can enter folder search mode by typing C-s and C-r in
  minibuffer.
* Off-line version of "x", namely "lx", is introduced.
* "x" became much faster thanks to a new algorithm of mew-dir-messages().
* A new range "sync" is defined.
* IMAP and NNTP are supported.
* +mdrop is renamed to $inbox.

## Differences between Mew 2.2 and Mew 2.1

* mew-summary-toggle-8bit is bound to "z8" instaed of "8".
* "0"-"9" are bound to digit-argument. So, for example, we can type
  "10d" instead of "C-u10d".
* yes-or-no-p is replaced by y-or-n-p.
* Minor bug fixes.

## Differences between Mew 2.1 and Mew 2.0

* XML is well supported.

* "c" in Summary works like "copy" (by specifying the current folder)
  while "o" does like "move".

* "," and C-cC-i are integrated. Use "," to display a part as it is.
  C-cC-i now acts like view-file.

* Both ":" and C-cC-l is now friendly for ":".

* +mdrop is implemented. You can remove messages on your POP server
  visually.

* Sort (s) and pack (O) became much faster.

* contrib/incdir now moves messages in the "cur" directory as well as
  the "new" directory if the "-a" option is specified.

* The "Type 'I'" message is displayed in the minibuffer, not in the body
  of a message marked with 'T'.

* The "Type 'T'" message is displayed in the minibuffer when CT: of an
  attach file is unknown and the default CT: is chosen.

* mew-case-guess-when-composed works well now.

* "Sort region" (C-uS) now revives.

* A header for a Bcc: message is now well-prepared.

* mew-thread-column is now obsoleted. Put 't' in mew-scan-form to
  specify the position of thread indentation.

* Asking Subject: before "Really send this message? ". And asking Fcc:
  if folders do not exist.

* The "phrase:addr1,addr2;" notation is allowed in Addrbook if and
  only if it doesn't recurse when expanded.

* Some workaround for broken POP servers.

* Many other small bug fixes.

## Differences between Mew 2 and Mew 1.94

* Mew 2 has thrown away Emacs 19, Mule 2.3, XEmacs 20.4.

* Mew 2 has thrown away IM and is being implemented purely by Elisp
  with two C commands, 'mewencode' and 'mewls'.

* Thread is supported. The key bindings of most thread commands 
  start with "t". For example, typing "tt" makes thread.

* Both Multipart/Alternative and Multipart/Related are supported.
  Use ":" to display the entire structure.

* Sophisticated POP support. POP biff is supported.

* 8bit clean. If mew-use-8bit is non-nil, 8bit charset in a body is
  sent without any MIME encoding(i.e. CTE: 8bit).  If this is nil,
  8bit charset in a body is sent with an appropriate MIME
  encoding(e.g. CTE: quoted-printable).  Also, 8bit messages to be
  attached are converted into 7bit.

  8bit messages to be signed are also converted into 7bit. This is
  required by the Multipart/Signed spec.

  mew-use-8bit is nil by default to avoid accidents.

* Preview. Typing C-cC-m in Draft mode puts the composed message to
  +queue. You can preview messages to be send in +queue with 
  Summary mode.	

  If you are in Summary mode, typing C-cC-c sends all messages in
  +queue. "i" in Summary mode also flushes all messages in +queue
  since mew-auto-flush-queue is default to t.

  Typing C-cC-c in Draft sends the draft without preview.

* MIME editor. Typing "E" (i.e. reediting) in Summary mode leads you
  Draft mode. If the target is multipart, attachments are prepared.

* In attachments, you can specify charset both for input and output.
  "C" specifies the charset parameter for a Text/* object.  
  "I" specifies a input coding-system for a text file.

* Header mode is created for resending and sending the same content
  to different destinations.

* C-cC-l makes use of autoconf of a specified language.

* Mew 2 is liberal for many kinds of broken messages.

## Differences between 1.94 and 1.93

* Auto input-method selection. Typing C-cC-y or C-cC-t in Draft mode
  automatically selects input-method on X/Emacs 20 or later.

  For example, Germany can be represented by both iso-8859-1 and
  iso-8859-1. When you received a Germany message in iso-8859-2, it
  would be nice if latin-2-postfix is selected for input-method. To
  implement this, put the following to your .emacs.

```elisp
(setq mew-charset-input-method-alist
      '(("iso-8859-1" . "latin-1-postfix")
	("iso-8859-2" . "latin-2-postfix")))
```

* "y" in Summary mode is now able to save the raw format of message
  (i.e. header fields are not decoded). You can safely forward saved 
  messages.

* Multiple "inbox"es with IM Config are supported.

* "D" in Summary mode removes all messages in the +trash folder.

* Summary mode is now really multi-lingualized thanks to IM.

* Aliases and Petname are integrated into Addrbook. To register expansion
  rules and/or personal information, type [C-u]C-cC-a in Summary
  mode.

* The cache prefetch mechanism is implemented. You can read messages
  very quickly in Summary mode.

* Thanks to the cache prefetch mechanism, the non-MIME analysis sub-mode,
  which is provided for rapid reading, becomes meaningless. So, M-a was
  throw away. Use "," if you want to see a message in the raw format.

* GNUPG support. To select PGPv2/PGPv5/GNUPG, type C-cC-v in Summary 
  mode.

* Imget's password and PGP passphrase can be cached. You can now survive
  without impwagent.

    - Set mew-use-cached-passwd t.
    - Set mew-use-pgp-cached-passphrase to t.

* C-c{C-s,C-p,C-b,C-r} can work even if draft contains attachments.

* Automatic PGP protection for all drafts or drafts replying to 
  encrypted messages is supported. 
  See mew-protect-privacy-{always,encrypted}.

* C-cC-p in Summary mode can handle old-fashioned PGP messages.

* "." can decrypt messages which you failed to decrypt before.

* Unknown Multipart/{Signed,Encrypted} is treated as a single part.

* C-u Z saves the update folder file to ~/Mail/.folders. So, Mew can 
  assume that this file exist by default. Concludingly the bootstrap
  becomes faster. mew-use-folders-file-p is now default to `t'. 

* You can customize Mew so that the directory previously used is 
  preserved. See, mew-{summary,draft}-preserve-dir. See also
  mew-summary-trace-directory.

* You can display text/html by a running netscape.
  Put the following in .emacs.

```elisp
(setq mew-prog-text/html-arg-hack 'mew-prog-text/html-netscape-remote)
```

* Range is asked only when you interactively execute "s".

* The key binding of FIB commands were changed with the C-cC-f prefix.

* Getting along with the mail-user-agent convention.

* Many IMAP4-friendly hacks.

* Many many bug fixes. And many many optimizations.

## Differences between 1.93 and 1.92

* Copyright of Mew conforms ``AS IS'' instead of GPL2.

* Mew now supports IMAP4 and qmail mailbox.

* immv, imrm, and imclean are implemented by Elisp. So, "x" in Summary
  mode became much faster. Other commands became faster as well.

* Multipart format in Summary mode and Draft mode are integrated.

* Neat support for IM Config. Please refer to info for more information.

* mew-opt-highlight-* -> mew-use-highlight-*.

* mew-field-{,in}visible were obsoleted. Use mew-field-spec instead.

* Hankaku kana is converted into zenkaku kana if exists.

* Safely ignores unknown charset in a header.

* message/partial and text/html are supported.

* Ad-hoc PGP 5 support.

* Content-Disposition: support.

* Neat reporting mechanism of PGP/MIME.

* Many many bug fixes.

## Differences between 1.93 and 1.70

* Mew uses IM Perl5 instead of MH. Mew will never support MH again.

* Mew works on OS/2, Win95, and WNT as well as on UNIX.

* Mew doesn't ask you to input y or n in Summary mode though it used
  to do so. Please follow instructions which Mew displays.

* Deleting messages on Summary mode(i.e. the D mark) means refiling to
  the +trash folder. If in +trash folder, messages marked with 'D' are
  really removed. You can customize this action. See
  mew-msg-rm-policy for details.

* "N" and "P" in Summary mode move the cursor onto only messages
  marked with '*'. To skip parts, call "n" or "p" with "C-u".

* The default folder name of draft changed from "+drafts" to "+draft"
  so that its length became equal to "+inbox" and "+trash".

* Some key-bindings in Draft mode were changed to keep C-c "key" for
  users.

  - C-cM  -> C-cC-a
  - C-cu  -> C-cC-l
  - C-cy  -> C-cC-t

* C-cC-u(undo) in Draft mode works for any kinds of messages. For this
  reason, mew-mime-compose-folder-delete is set 'delete by default.

* PGP/MIME became very stable. And verification message turned more
  informational.

	e.g. "No public key" -> "No his/her public key"

  C-cC-u works even for PGP shortcuts.

* Refile scheme was changed much.

    - mew-auto-folder-alist             -> mew-refile-guess-alist
    - mew-refile-folder-guess-functions -> mew-refile-guess-control

* Pick interface(for "?", "/", and "V") was changed. Examples are below:

```
to=mew-dist
to=kazu & cc=kazu
```

* Burst("B") on Summary mode is now really cool.

* Subject is displayed for Message/Rfc822 if Content-Description: is empty.

* "C-uZ" on Summary mode saves Mail/.folders if mew-use-folders-file-p. 
  If mew-use-folders-file-p is t, Mew loads Mail/.folders at boot time.

* Many similar codes were integrated.

* Some function names were changed.

    - mew-mark-process-all-folders -> mew-mark-clean-up-all
    - (Remove kill-emacs-hook from .emacs if it contains
    - mew-mark-process-all-folders.)

* Some variables were changed.

    - Each members of mew-folders-ignore must start with "+" or "=".
    - Value of mew-folders-default-folder must start with "+" or "=".

* Support RFC 2047(aka MIME header encoding/decoding) precisely.

* Color is now used by default. Remove configurations concerned with
  fonts from each hooks!.

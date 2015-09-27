---
layout: default
class: Macro
title: base64 ';' FILEPATH (';' LIMIT)?
summary: The Base64-encoded contents of a file
---
layout: default

**Since: bnd 3.1**

Retrieves the content of the file specified by FILEPATH and embeds it in the manifest in Base64-encoded form. E.g.:

    # construct a data: URL for an icon file (cf IETF RFC 2397)
    Icon-Url: image/gif;base64,${base64;icons/myicon.gif}

Obviously it is best only to do this with *small* files, such as 16x16 icons.

The optional LIMIT parameter specifies the maximum length (character count) of the encoded data. If the length would exceed
this limit, an error is raised.

    Icon-Url: image/gif;base64,${base64;icons/myicon.gif;1000}

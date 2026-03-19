---
layout: post
title:  "Public Key Generated"
date:   2026-03-18 22:15:42 -0500
categories: gpg update
---

I have generated a key via GPG; this, in short, means I can now sign and encrypt stuff. Now you can know if it actually is me releasing/signing stuff. The key is hosted on the OpenPGP keyserver, and its fingerprint is `D53B7C199620E19314387D004E23E7D1BE44FB14`.

## How To Import

### via command line

{% highlight bash %}
gpg --recv-keys D53B7C199620E19314387D004E23E7D1BE44FB14 --keyserver hkps://keys.openpgp.org
{% endhighlight %}

### via Kleopatra

Set your keyserver to hkps://keys.openpgp.org via Configure Kleopatra:

![Go to Settings, then Configure Kleopatra, then paste the keyserver into Directory Services](/images/2026-03-19-made-public-key/set_keyserver.gif)

Next, lookup `zach10smith@proton.me` (my development email) on the server, and select the one with the name on it that comes from the keyserver (not WKD). This should start with `D53B 7C19 9620 E193 1438`:

![Go to File, then Lookup On Server, then search the email provided. Select the Keyserver key.](/images/2026-03-19-made-public-key/lookup_on_server.gif)

Finally, import the key.

## Closing

You should be all set now. You can now verify signatures on stuff I provide (like files).

With Kleopatra, you should just be able to download the signature file, put it in the same directory as the file, and double click the signature file to verify.

With GPG, run:

{% highlight bash %}
gpg --verify {signature}
{% endhighlight %}

Replacing {signature} with the signature file.

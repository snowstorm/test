#faketag - the android based emulator of nfc tags 

Goal of this project is to create a simple android based emulator for nfc tags.
Processing of APDU's is based on a simple json file.

##JSON file format

This emulator is processing apdu commands based on simple JSON files. Use the following format:

```json
[
	{"request":"80CA9F7F00","response":"6800"},
  	{"request":"12345","respone":"12345"}
]
```

The response values must be base64 encoded at the moment as they were dumped with my fork if bakomatinfos. See "How to create JSON dump" below.

So if you sniff sessions from real world nfc-tags you can generate a json-file like the above and
your able to emulate this nfc tag. At the moment only statically tags without any random data are 
supported.

You have to place the file into your ExternalStorageDirectory which you'll find with using:
```Java
Environment.getExternalStorageDirectory()
```

use ```json faketag.json``` as filename. 

### How to create JSON dump?

I've added the functionality to dump your credit card into the faketag JSON file format with bankomatinfos. 
This is a great and useful tool originally created by John Zweng.
See here: https://github.com/kairenken/bankomatinfos 
Just activate the "dump nfc tag function" under settings. 

<img src="https://github.com/kairenken/faketag/blob/master/img/Screenshot_2015-03-09-09-42-56.png" alt="disabled NFC" width="300"/>
<img src="https://github.com/kairenken/faketag/blob/master/img/Screenshot_2015-03-09-09-43-02.png" alt="enabled NFC" width="300"/>




[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/asheroto)
# Converting images to BIMI accepted format

The BIMI check/validation websites kept complaining that my SVG didn't pass the specification.

I tried using a few sites to convert the image, but it still failed the validation regardless.

Here's how I ended up getting it to work.

**First, download these two binaries:**
- [png2svg.exe](https://github.com/asheroto/bimi-svg-conversion/releases/latest/download/png2svg.exe)
- [SvgTinyToSvgTinyPS.exe](https://github.com/asheroto/bimi-svg-conversion/releases/latest/download/SvgTinyToSvgTinyPS.exe)

**Next**, open up PowerShell/Command Prompt in the directory the EXEs are located and enter this command to convert your PNG image to SVG:
- `png2svg.exe -v -l -o yourImage.svg yourImage.png` (yes, the destination file first)

**Then** just launch `SvgTinyToSvgTinyPS.exe` as it is a GUI application. Specify the SVG and final SVG name, specify the title (usually company or website name) and click Generate!

The DNS record is a TXT record on the root. At most DNS providers, you just specify `@` for the record name and the following for the value, changing the path of the SVG file as needed.

`v=BIMI1;l=https://yourdomain.com/img/bimi_icon.svg;`

A valid DMARC record is required as well. As an example, here is a valid DMARC record:U

`v=DMARC1; p=quarantine; rua=mailto:security@yourdomain.com; ruf=mailto:security@yourdomain.com; sp=none; fo=1;`

😎

![png2svg.exe example](https://i.imgur.com/vpXjTFw.png)

![SvgTinyToSvgTinyPS.exe](https://i.imgur.com/RdYcsWA.png)

![MXTOOLBOX BIMI Validation](https://i.imgur.com/SXxnRnU.png)

## Validate BIMI record and SVG image

Man I love MXTOOLBOX.

[https://mxtoolbox.com/bimi.aspx](https://mxtoolbox.com/bimi.aspx)

## Sources

If you want to compile or grab the files manually, here are the projects the EXEs came from. You don't need to do this unless you want to, the above files are just the compiled forms of these projects.
- [png2svg](https://github.com/xyproto/png2svg)
- [svg-ps-converters](https://github.com/authindicators/svg-ps-converters/)
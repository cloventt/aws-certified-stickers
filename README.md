# AWS Certification Stickers
I got frustrated by the fact that AWS only seems to publish low-res rasterized versions of their
AWS certification badges, so I re-created them in Inkscape.

## Usage
There are two files in the root of this repo, both called `A4-sticker-sheet-all-badges`.

The EPS file can be loaded by Roland VersaStudio software or probably whatever software your cutter does. The PDF
version is the same thing, but published for viewing on your computer. I haven't actually tested any of this so YMMV.

## Development
The primary template file is `AWS-certified-badge-template.svg`. This is an Inkscape SVG project/image. For it to work properly you need to have the AWS fonts installed
on your system. You can find them [here](https://developer.amazon.com/en-US/alexa/branding/echo-guidelines/identity-guidelines/typography).

Inkscape cannot handle the CMYK colorspace properly. This isn't a limitation with Inkscape but the underlying Cairo
SVG library it is using. This only really matters when you want to print some stuff you designed in Inkscape - specifically
with the magic magenta cutline that most cutters read to decide where to cut. We have to do an annoying post-conversion step 
using Scribus to force the magic magenta cutline to be a _true_ CMYK magenta spot colour. If I cared more or updated this 
frequently I would script up something to do all this for you, but for now the manual process is tolerable enough.

To create a printable file similar to the A4-sticker-sheet file:

1. Generate your SVG file with/without cutline, up to you.
2. Using [Scribus](https://en.wikipedia.org/wiki/Scribus) create a new document for printing.
3. In Scribus use File -> Import -> Get Vector File to ad your badge(s) to the page. 
4. Once you are happy with the page, go to Edit -> Colours and Fills
5. Find the `FromSVG#ff00ff` colour - this is the closest Inkscape can get to the magic Magenta cutline colour.
6. Select the colour and go Edit.
7. Change the Colour Model dropdown to `CMYK`, tick the `Is Spot Colour` box, and make sure the colours are 100% magenta and 0% anything else.
8. Click OK and save your file as an EPS (Encapsulated Postcript) document.

This should then print pretty easily on any post-script capable printer. In theory printer/cutters like the Roland Versastudio can print
and use the cutline (I haven't tested this yet).

You can use these template files to create printed vinyl stickers of the badges. Or do whatever you want,
I don't own them, all copyright belong to Amazon and our overlord the almighty Bezos.


## Stickers and Icons

I have also included pre-baked SVGs of all the badges in the `stickers/` folder.

![Cloud Practitioner Foundational](stickers/CloudPractitionerFoundational.svg?raw=true) ![Solutions Architect Associate](stickers/SolutionsArchitectAssociate.svg?raw=true) ![SysOps Administrator Associate](stickers/SysOpsAdministratorAssociate.svg?raw=true) ![Developer Associate](stickers/DeveloperAssociate.svg?raw=true) ![Data Engineer Associate](stickers/DataEngineerAssociate.svg?raw=true) ![Solutions Architect Professional](stickers/SolutionsArchitectProfessional.svg?raw=true) ![DevOps Engineer professional](stickers/DevOpsEngineerProfessional.svg?raw=true) ![AdvancedNetworkingSpecialty](stickers/AdvancedNetworkingSpecialty.svg?raw=true) ![Data Analytics Specialty](stickers/DataAnalyticsSpecialty.svg?raw=true) ![Database Specialty](stickers/DatabaseSpecialty.svg?raw=true) ![Machine Learnine Specialty](stickers/MachineLearningSpecialty.svg?raw=true) ![Security Specialty](stickers/SecuritySpecialty.svg?raw=true) ![SAP on AWS Specialty](stickers/SAPOnAWSSpecialty.svg?raw=true)

# Cisco CML Notes 

# Upload  reference platforms ISO Refplat to CML

<p>1.- Download the refplat-20250616-fcs-iso.zip
<p>2.- in VMware CML virtual machine settings go to cd/dvd and brose the refplat-20250616-fcs.iso
<p>3.- select connect and connect at power on
<p>4.- Go to CML cockpit 
<p>5.- in CML2 secction find copy refplat iso
<p>6.- click on refplat iso booton 


# Upload Images to cml with scp

- Location to upload qcow2 images in cisco CML
  /var/local/virl2/dropfolder/image.qcow2

- Location where CML has all the images
  /var/lib/libvirt/images/virl-base-images/"image-folder"/image.qcow2

- upload a image with csp command:
  scp image.qcow2 admin@10.1.1.1:/var/local/virl2/dropfolder/


# Create a qcow2 image from a ova file

- Extract the vmdk file from the ova file
  tar -xf UCSPE_4.2.2aS9.ova UCSPE_4.2.2aS9-disk1.vmdk

- Convert the vmdk to qcow2
  qemu-img convert -c -f vmdk -O qcow2 UCSPE_4.2.2aS9-disk1.vmdk ucspe_4.2.2aS9s.qcow2

  <p>-c is to compress the file
  <p>-f to indicate the origin file format
  <p>-O to indicagte the destination file format
   

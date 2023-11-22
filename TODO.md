!!! Another approach !!!
 - https://github.com/sprotheroe/vagrant-disksize
$ agrant plugin install vagrant-disksize
Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/xenial64'
  config.disksize.size = '50GB'
end


 + https://askubuntu.com/questions/317338/how-can-i-increase-disk-size-on-a-vagrant-vm/1402237#1402237
# Resize your LVM logical volume to fill the available Free space.
$ sudo lvdisplay
--- Logical volume ---
  LV Path                /dev/ubuntu-vg/ubuntu-lv
  
$ sudo lvextend -l+100%FREE /dev/ubuntu-vg/ubuntu-lv

# Apply the changes to the filesystem.
> sudo resize2fs /dev/ubuntu-vg/ubuntu-lv
> df -lhT /


[ ] Increase disk size to 64GB - $export VAGRANT_EXPERIMENTAL="disks" $vagrant up
[ ] [Add Angular IDE](https://dzone.com/articles/creating-your-first-angular-4-app-using-angular-id-1?edition=317406&utm_source=Weekly%20Digest&utm_medium=email&utm_campaign=Weekly%20Digest%202017-08-23)

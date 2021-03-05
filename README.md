# Vagrant Ansible SigStore rekor setup

Vagrantfile using an Ansible role to test
[SigStore](https://github.com/SigStore)'s rekor server.

## Usage

A `Vagrantfile` is available for provisioning virtual machines for local
testing.

Clone the repository and then simply run with the following additional args
added to the `vagrant` command:


* `--instances`: The number of Keylime Virtual Machines to create. If not provided, it defaults to `1`
* `--repo`: This mounts your local Keylime git repository into the virtual machine (allowing you to test your code within the VM). This is optional.
* `--cpus`: The amount of CPU's. If not provided, it defaults to `2`
* `--memory`: The amount of memory to assign.  If not provided, it defaults to `2048`
* `--qualityoflife`: Adds a few extras, such as the Powerline improved bash shell
   prompt as well as an ls alias (ll for ls -lAh). This is optional.

Deployment example, using libvirt as the virtualization provider:

```
vagrant --instances=2 --repo=/home/jdoe/keylime --cpus=4 --memory=4096  up --provider libvirt --provision
```

Deployment example, using VirtualBox as the virtualization provider:

```
vagrant --instances=2 --repo=/home/jdoe/keylime --cpus=4 --memory=4096  up --provider virtualbox --provision
```

| NOTE: Customized args (`--instances`, `--repos` etc), come before the main Vagrant args (such as `up`, `status`, `--provider`). Example: To `ssh` into the second machine instance, keylime2, use the Vagrant command as such : `vagrant --instances=2 ssh keylime2`|
| --- |

If you would like to customise these defaults without having to specify them on
the command line each time, you can use a `vagrant_variables.yml` file. The
simplest way to do this is to copy `vagrant_variables.yml.sample` to
`vagrant_variables.yml` and edit it:

```shell
cp vagrant_variables.yml.sample vagrant_variables.yml
```

You can still override the defaults in `vagrant_variables.yml` by using the
command line options.

Once the VM is started, use `vagrant ssh` to ssh into the VM and run `sudo su -`
to become root.

You can then start the various components using commands:

```
TODO
```

## License
[Apache
2.0](https://github.com/SigStore/rekor-vagrant-ansible/blob/master/LICENSE)

## Contribute

We welcome contributions and pull requests are welcome!

## Contributors

* axel simon (axel@redhat.com)

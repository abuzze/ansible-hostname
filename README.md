# Ansible Hostname

By including this role, it will set the hostname of the server to the same as the variable `hostname`. If the variable isn't defined, it will skip all steps.

In addition to setting the hostname in `/etc/hostname`, it will add a line to the server's `/etc/hosts` to avoid `sudo: unable to resolve host` and other related warnings/errors.

## Usage

Requires `sudo` or root access.

I like to include the hostname in my inventory file:

```ini
[workers]
192.168.33.101 hostname=app-worker-01
192.168.33.102 hostname=app-worker-02
192.168.33.103 hostname=app-worker-03
```

Then include the role in my provising playbook.

```yaml
  hosts: workers
  sudo: yes

  roles:
    - jyunderwood.hostname
```

## License

This Ansible role is licensed under the MIT License.

Copyright (c) 2015 Jonathan Underwood

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

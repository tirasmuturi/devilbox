.. _example_setup_phalcon:

*************
Setup Phalcon
*************

This example will use ``phalcon`` to install Phalcon from within the PHP container.

.. seealso:: `Official Phalcon Documentation <https://docs.phalconphp.com/en/3.2/devtools-usage>`_


**Table of Contents**

.. contents:: :local:


Overview
========

The following configuration will be used:

+--------------+--------------------------+-------------+------------+-----------------------+
| Project name | VirtualHost directory    | Database    | TLD_SUFFIX | Project URL           |
+==============+==========================+=============+============+=======================+
| my-phalcon   | /shared/httpd/my-phalcon | n.a.        | loc        | http://my-phalcon.loc |
+--------------+--------------------------+-------------+------------+-----------------------+


Walk through
============

It will be ready in six simple steps:

1. Enter the PHP container
2. Create a new VirtualHost directory
3. Install Phalcon
4. Symlink webroot directory
5. Setup DNS record
6. Visit http://my-phalcon.loc in your browser


.. seealso:: :ref:`available_tools`


1. Enter the PHP container
--------------------------

.. code-block:: bash

    host> ./shell.sh

.. seealso:: :ref:`tutorial_work_inside_the_php_container`


2. Create new vhost directory
-----------------------------

.. code-block:: bash

    devilbox@php-7.0.20 in /shared/httpd $ mkdir my-phalcon


3. Install Phalcon
------------------

.. code-block:: bash

    devilbox@php-7.0.20 in /shared/httpd $ cd my-phalcon
    devilbox@php-7.0.20 in /shared/httpd/my-phalcon $ phalcon project phalconphp


4. Symlink webroot
------------------

.. code-block:: bash

    devilbox@php-7.0.20 in /shared/httpd/my-pahlcon $ ln -s phalconphp/public/ htdocs


5. DNS record
-------------

If you do not have :ref:`global_configuration_auto_dns` configured, you will need to add the
following line to your host operating systems ``/etc/hosts`` file
(or ``C:\Windows\System32\drivers\etc`` on Windows):

.. code-block:: bash
   :caption: /etc/hosts
   :name: /etc/hosts

    127.0.0.1 my-phalcon.loc

.. seealso::
    For in-depth info about adding DNS records on Linux, Windows or MacOS see:
    :ref:`project_configuration_dns_records` or :ref:`global_configuration_auto_dns`.


6. Open your browser
--------------------

Open your browser at http://my-phalcon.loc

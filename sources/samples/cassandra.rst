:title: cassandra-buildsample
:description: A brief description about cassandra-buildsample
:keywords: cassandra, Language,services,Install

.. _cassandra:

Cassandra-buildsample
=====================

The goal of this code sample is to show you how to set up and run your repo in shippable.

A sample repository `cassandra-buildsample <https://github.com/Shippable/cassandra-buildsample>`_ has been created using ruby.  

We need the yml file to analyze the project details. Add the shippable.yml file to the root of your repo by specifying:


**language :** Specify the language used to create the project. Ruby is used in this sample project.

**services :** Specify the service required for this sample code using "services" tag.

**install :** Install the required dependencies for your repo here.

**script :** Execute the sample code using script tag. 

Here is the complete yml file for cassandra-buildsample

.. code-block:: bash
   
   language: ruby
   
   services:
     - cassandra

   install:
     - gem install cassandra

   script:
     - cassandra-cli -host localhost -port 9160 -f schema.txt
     - ruby sample.rb
     - cassandra-cli -host localhost -port 9160 -f removeKeyspace.txt 
   
     
Enable the repo cassandra-buildsample and run it using an Ubuntu minion. Once the build finishes execution, you can check for the console output on the respective build's page.



---
layout: page
title: Resource
permalink: /resource/
---
<h3>1. Computational resources </h3>
Penn State hosts the high-performance computing computing (HPC) infrastructure, referred to as 
<a href="url">Roar supercomputer</a>. Roar provides secure, high-quality advanced computing and storage resources to the Penn State research community. Request of resources can be done in the following approaches (Content adapted from the <a href="https://www.icds.psu.edu/computing-services/roar-user-guide/"> user guide</a>). 

<h4> 1.1 Open queue vs. reserved allocation </h4>

<p class="noindent">All Penn State students, faculty and staff are able to run on the Roar “open queue” on ACI-b for no charge. The current limits per user on the open queue are:</p>
<ul>
<li class="noindent"><span class="normaltextrun"><span lang="">100 jobs pending</span></span></li>
<li class="noindent"><span class="normaltextrun"><span lang="">100 cores executing jobs at any given time</span></span></li>
<li class="noindent"><span class="normaltextrun"><span lang="">48-hour job wall-times</span></span></li>
<li class="noindent"><span class="normaltextrun"><span lang="">24-hour interactive session durations</span></span><span class="eop"><span lang="">&nbsp;</span></span></li>
</ul>

To run jobs with longer/higher request of resources, one need to turn to allocated resources, which are guaranteed to start within 1 hour. Please reach out to the PI for information of the allocation.

 <h4> 1.2 Interactive session </h4>
 Interactive sessions are great fit for debugging, testing, and running small jobs. One can request some interactive resources from ACI-b on the login terminal via the following command (1 hour, 2 cores),
 
<p><code>qsub -A open -l walltime=1:00:00 -l nodes=1:ppn=2 -I</code></p>


<h4> 1.3 Non-interactive request </h4>
After testing the correctness of a sample sript using an interactive session, it's usually a good idea to switch to non-interactive run for more serious calculations requiring extended stable resources. One may submit jobs via *qsub*, here is an example script using the open queue,
<pre class="script">#!/bin/bash
#PBS -N LAMMPS_RUN
#PBS -A open
#PBS -l walltime=04:00:00
#PBS -l nodes=2:ppn=20
#PBS -j oe
module load gcc/5.3.1 mpich/3.2
cd $PBS_O_WORKDIR
mpirun  /path/to/lammps_mpi  < in.script
</pre>


<h4> 1.4 OnDemand </h4>
ACI-i provides a set of interactive cores which may only be accessed via <a href="https://www.icds.psu.edu/userguide/05-00-basics-aci-resources/05-04-connecting-aci/05-041-open-ondemand/"> Open OnDemand</a>.  
Often ACI-i is used to develop and test small scale test cases due to the ability to use a graphical user interface. Once the model has been developed, it can be submitted as a job to ACI-b to take advantage of the greater computational resources available on ACI-b.  
<p class="indent">Individual processes are limited to</p>  
<ul class="itemize1">
<li class="itemize">4 processors</li>
<li class="itemize">12 CPU hours per process</li>
<li class="itemize">48 GB resident memory</li>
</ul>




 


  

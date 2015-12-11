---
layout: post
title:  "Another post!"
date:   2015-12-11 17:16:16 +0000
categories: open launch
---

This is the another post within the Open portal, now being used with Git to pull changes.

Incidentally, this portal is built using [Jekyll][jekyll], a really neat way to build fast websites.

<div class="note info">
  <h5>Built with Jekyll</h5>
  <p>
    The site was build using docker, and this post was written with `nano` and then the site built and launched with `jekyll server`.
  </p>
</div>

I'm really interested in showing a code snippet, so here is hopefully some PowerShell:

{% highlight powershell %}
$port= new-Object System.IO.Ports.SerialPort COM5,115200,None,8,one
$port.Close();
$port.Open();
$path = Split-Path $MyInvocation.MyCommand.Path

while($true)
{
    $line = $port.ReadLine();
    Write-Host $line

    if($line -like "BUT1*") 
    {
        Write-Host "Starting Type Scene"
        invoke-expression -Command "$path\DispTypeOnAir.ps1"   
    } 
    
    if($line -like "BUT4*") 
    {
        Write-Host "Starting Cued Item"
        invoke-expression -Command "$path\StartCuedOnAir.ps1"   
    } 

    
}

{% endhighlight %}

[jekyll]: http://jekyllrb.com

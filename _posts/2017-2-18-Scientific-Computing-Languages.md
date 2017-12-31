---
layout: default
title: "Scientific Computing Languages"
---

As a Master's student it is common to either recreate existing algorithms in papers or to develop your own, in the past Python was my go to language for this task since it had clean pseudocode like syntax, all the built in data structures, and a wide variety of libraries implementing a portion of the common functions used in algorithms. However, about 6 months I started to try out Julia which is a language designed for scientific computing. I figured I'd give it a go but then switch back to Python finding it to not be mature enough but here we are I'm still using now and have been making it my default language for implementing algorithms. 

If you've not tried Julia and are currently a Python user here is why should considering switching. Julia provides a lot of math functions straight out of the box without even importing the math library. Secondly, it has proper arrays built straight in, but due to some clever syntax they provide much of the functionality of Python's list, including comprehensions but without all the additional processing that comes along with it. The last and perhaps most important benefit is the significant performance difference it allows. Python is always known to be relatively pokey in terms of performance and I've found myself on more than a few occasions having to move to another language in order to scale up to larger data sets or larger chunks of data which means I have some throw away code. I've written far less throw away code with Julia.  Below I decided to some testing to generate some quantitative data. I began by programming the same quick sort algorithm in both languages, generating some random numbers and running them both through each program. What I found is summed up in the chart below. Using large datasets Julia is substantially faster. 
Quick Sort on Randomly Generated Numbers

JuliaPython
Note the issues Python has Scaling up to larger sets of numbers, where Julia maintains reasonable performance
In terms of library support Python still has more libraries natively but I haven't found this to be much of an issue since I've found that for most things Julia actually has them built in, normally with Python you have pass along instructions with what libraries one must install before running your script, the standards are of course numpy for matrices and possibly a few others for math libraries. Most times with Julia I can write algorithms with no imports at all, huge bonus!

 

The syntax is very similar between the two as well making the jump relatively straight forward and since Julia has all the lovely list comprehensions you can keep those super short snippets of code. I also found my code even shorter since I wasn't jumping back and forth between lists and numpy. 
```julia
function hist(img)
    dx, dy = size(img)
    hist = zeros(Int16, (dx,dy))
    for i=1:dx j=1:dy
        hist[img[i,j]+1] += 1
    end

    return hist
end
def hist(img):
   hist = numpy.zeros(len(img), len(img[0]))
    for i in img:
        for j in img[i]:
            hist[j] += 1
    return hist
```
Above is an example of calculating the histogram of an image, note how similar the syntax is and how short both code samples are, also note that no external libraries were used with Julia but numpy was needed for the matrix in the Python sample. 

For scientific computing I have really found Julia to be a far better option, and I'd recommend that you give it a try for your next project.

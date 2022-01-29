---
layout: post
title: "Why complex signals?"
date: 2022-01-28 16:45:42 +0800
categories: [academic]
comments: false
---
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.15.2/dist/katex.min.css" integrity="sha384-MlJdn/WNKDGXveldHDdyRP1R4CTHr3FeuDNfhsLPYrq2t0UBkUdK2jyTnXPEK1NQ" crossorigin="anonymous">
<script src="/Gennadiyev/assets/js/katex.min.js"></script>
<script src="/Gennadiyev/assets/js/katex-auto-render.min.js"></script>

<!-- Begin of document -->

After I've just narrowly passed the final for [Signals and Systems](https://eess.sjtu.edu.cn/Default.aspx) - a really nonsense lecture never being able to teach me anything useful, I decided to make a brief recap on it because the *Pro Plus* version of the course is upcoming next term: Digital Signal and Image Processing.

I purchased a textbook on digital signal processing and began to wonder how and why we've been using complex (imaginary) signals all the time. For example, we always use the following signal as our input:

$$x(n) = e^{\mathrm{j}\omega n}$$

But why? How does a complex signal make any sense, given that ordinary signals are simply measurable real-valued voltages?

After investigating into this issue both online and from the textbook, here is my personal understanding.

## From 3D Sinusoidal Signal...

<div id="ggb3d1" style="height:400px; width:600px; font-size:0">
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
</div>

Shown above is an interactive example illustrating a discrete signal $x(n)=Ae^{\mathrm{j}\omega n}$. Using Euler's Formula,

$$x(n) = A \cos (\omega n) + \mathrm{j} \sin (\omega n)$$

This means that $x(n)$ has an imaginary value for each sample at $n$. But what does a signal with $3+\mathrm{j}4$ exactly means?

I sincerely invite you (especially if you have yet to take related courses) to **pause here and think over the problem yourself**.

## ...to a 2D Sinusoidal Signal

If you've put some thoughts into it, you may discover that having an imaginary signal means that the signal is containing twice as much information as compared to a classic sinusoid. Actually you are correct!

When you are transmitting a sinusoid, not only amplitude information ($A$) is sent, but also a phase offset $\phi$ can be modulated. These are two separate **channels** of information transmission.

Consider the classical sinusoid:

$$x(n)=A\cos(\omega n + \phi)$$

Both $A$ and $\phi$ can be modulated by the source, and can be used to transmit information. Because the two channels are **fully-independent** (or fancier, **orthogonal**), people then use the imaginary space to denote the signal:

$$\operatorname{Re}(A e^{\mathrm{j}\phi} \cdot e^{\mathrm{j}\omega n})=A\cos(\omega n + \phi)$$

A complex value of a signal explains both the amplitude and the phase of the signal:

$$A \cos(\omega n + \phi) = A_1 \sin (\omega n) + A_2 \cos (\omega n)$$

From this we can derive both the amplitude and phase of $x(n)$. The amplitude is given by the amplitude of the complex value:

$$A = \sqrt{A_1^2 + A_2^2}, \phi = \arctan\left(\dfrac{A_2}{A_1}\right)$$

which can then be used to draw the famous Bode's Plot of the signal.

## And Finally, the Exponential Form

Nobody likes to represent signals in the form of vectors (as in $\displaystyle{\left(\begin{matrix}
A_1 \\ A_2\end{matrix}\right)}$), but it is possible to represent them in the form of a $x(n) \Big|_{n=n_0} = Ae^{\mathrm{j}\omega}$. In this way, we can represent the amplitude and phase angle in one single complex number, and meanwhile getting rid of the awkwardness of $\arctan$.

Summing up, the exponential form of a signal is a shorthand to represent **two orthogonal channels of analog signals**: amplitude and phase.

Recall what we've learned from the circuit analysis course:

$$U_1 = 3 + \mathrm{j} 4 \approx 5 \angle 53^{\circ} = 5\sin(\omega t + 53^\circ)$$

The real part and the imaginary part are not important in signal and systems. Instead, the phase angle $\phi = 53^\circ$ and the amplitude $A = \sqrt{3^2 + 4^2}=5$ are important.

And this puts an end to the mystery of the exponential form of a signal.

<!-- End of document -->

<script>
    document.addEventListener("DOMContentLoaded", function() {
        renderMathInElement(document.body, {
            delimiters: [
                {left: '$$', right: '$$', display: true},
                {left: '$', right: '$', display: false},
                {left: '\\(', right: '\\)', display: false},
                {left: '\\[', right: '\\]', display: true}
            ],
            throwOnError : false
        });
    });
</script>

<!-- Write GGB -->
<script src="/Gennadiyev/assets/js/ggb123.js" crossorigin="anonymous"></script>
<script>
window.onload = function() {
    for(var i=0; i<100; i++){
        var si3d = i.toString();
        var ggbid3d = document.getElementById("ggb3d"+si3d);
        if(ggbid3d){
            var para3d={
                "width":ggbid3d.offsetWidth, 
                "height":ggbid3d.offsetHeight,
                "enableRightClick":true, 
                "borderColor":"white", 
                "ggbBase64":ggbid3d.innerText
            };
            var applet3d = new GGBApplet(para3d, '5.0');
            applet3d.inject('ggb3d'+si3d);
        }
    }
    for(var i=0; i<100; i++){
        var si = i.toString();
        var ggbid = document.getElementById("ggb"+si);
        if(ggbid){
            var para={
                "width":ggbid.offsetWidth, 
                "height":ggbid.offsetHeight,
                "enableRightClick":false, 
                "enableShiftDragZoom":false, 
                "enableLabelDrags":false, 
                "borderColor":"white", 
                "ggbBase64":ggbid.innerText
            };
            var applet = new GGBApplet(para, '5.0');
            applet.inject('ggb'+si);
        }
    }
}; 
</script> 

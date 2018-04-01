---
layout: szhang_note
category: notes
math: true
title: 二维AOD调研
---

## How Nigg used AOM:

0. shift laser frequency
1. in Laser locking system: "noise eater", high bandwidth frequency control
2. shift laser frequency of the $\sigma_+$ & $\pi$ in Raman Operation


## How Hempel used AOD for addressing:

### Two traps

* I: initially to investigate $^{43}\mathrm{Ca}^+$
* II: $^{40}\mathrm{Ca}^+$ & $^{44}\mathrm{Ca}^+$ two-ion crystal (What's that?)


### AC Stark in a composite pulse sequence:
* AOD (_Gooch&Housego, model 45070-5-6.5DEG-633_)
	* frequency detuning between $-50 \sim -90 \mathrm{MHz}$

	* __Key addition__ 
		* Trap II is able to address individual ions in long string, equipped with AOD.
		* Trap I used offset voltage to shuttle the desired ion into the tightly focussed addressed beam over a distance of $10 \mu\mathrm{m}$ within $40 \mu\mathrm{s}$. This is impractical for longer strings.

	| AOM | AOD |
	|:---:|:---:|
	| speed | large diameter, highly collimated beam |
	| extinction ratio | lower $v_a$ for larger number of resovable spots <br> thus _shear mode_ (acoustic wave in the direction [110] in $\mathrm{TeO}_2$) is used |

* EOD (the EOD used is from *Leysop Ltd., United Kingdom*) used on $^{40}\mathrm{Ca}^+$ linear trap
 	- switching speed (~30$\mu\mathrm{s}$) is given by the time it takes to (dis)charge the deflector's electrodes, and is thus mainly determined by "the amount of current the high voltage amplifier used to drive the device can deliver" (I recognize it as a particular maximal current intensity?).
 	- **deflection range is limited** to $3\sim 5 \mathrm{mrad/kV}$ 

#### The paper Hempel cited about EOD: [New J. Phys. 15 123012](http://dx.doi.org/10.1088/1367-2630/15/12/123012)
* Switching event between neighboring ions takes $15\mu\mathrm{s}$.
<center>
	![](https://www.iontrap.net/-/pic/AOD-investigation-7a.PNG)<br>Time dependence of the voltage on the EOD switching between two neighboring ions.
</center>

* **Phase changing** keeps for $>100\mu\mathrm{s}$ after switch, but that doesn't affect the ac-Stark effect.
* Calibration routine (Accuracy of 50nm):
<center>
	<img src="http://www.iontrap.net/-/img/AOD-investigation-7a.PNG" width="400">
	<img src="http://www.iontrap.net/-/img/AOD-investigation-9.PNG" width="300">
</center>
	1. With the mortorized lens, move the beam onto the center of the ion string
	2. Find the EOD voltages for every individual ions. Fit a Gaussian envelope to the excitation rate as a function of the (?)lens position(?) (Why not as a function of EOD voltage?). 


### OD qualification:
* deflection range $\Delta \phi = \lambda \Delta f/v_a$ -- $\Delta f$ ~ AO bandwidth; $v_a$ ~ acoustic wave velocity
	* rf.vl. $\mathrm{RF:} f_0=70\mathrm{MHz}, \Delta f=40\mathrm{MHz}, \Delta \phi=47\mathrm{mrad}$
* number of resovable spots $N = \frac{\pi}{4}\frac{D\Delta f}{v_a}$
* switching speed: just acoustic transit time $\tau_a = D/v_a$. 
	 - low enough to avoid motional heat during ion transport
	 - high enought to allow arbitrary addressing
* focus position resolution , rf.vl. $3.79\mu \mathrm{m/MHz}$
* 1st order diffraction efficiency, rf.vl. At $633\mathrm{nm}$ for $0.7\mathrm{W}$ RF, plateau of $92%$ over $\pm 10\mathrm{MHz}$ around $f_0$ with a fall-off to $\sim 72%$ at the $\pm 20\mathrm{MHz}$ band edges.


## Kumph thesis:
* *2D Arrays of Ion Traps for Large Scale Integration of Quantum Information Processors*
* $^{40}\mathrm{Ca}^+$
* No AOD
* AOM used in
	- control the power and frequency of the lasers (double-pass) 397nm, 729nm, 854nm, 866nm, PC controlled.
	- zero's mode for the 397nm laser beam to reach the ions for far detuned cooling

	I'm sure neither AOD nor AOM are used as deflector

* How addressing is conducted (By _address_ it means _turn on and off_?)
	- Fig. 3.6

## Options

### Gooch & Housego

#### Standard
* Acousto-Optic Beam Deflector for UV systems [(AOBD-UV) 3246 or **3283**](https://goochandhousego.com/wp-content/uploads/2016/04/GH-AO-UV-Beam-Deflector.pdf). (3283 is prefered.)
	* Both of them work on 355nm and have 1% insertion loss.
	* Acoustic velocity in the crystal: $5.74\mathrm{mm/\mu s}$.
	* Transition time depends on diameter of the beam: $\Delta t = 175\mathrm{ns/mm} d_{beam}$.
	* The major difference between 3246 and 3283 is RF bandwidth, and thus scan angle. In addition, 3283 has a more flat diffraction efficiency. In order to cover a $40\mu\mathrm{m}$ range,
		* 3246: 4.9mrad ~ distance=8.2mm
		* 3283: 1.2mrad ~ distance=33mm
	* > 2D UV beam scanning may be achieved by cascading two UV deflectors in series. Our flexible functionality **AODF Dual Driver** with phase synchronized outputs offers the optimum in RF driver control for 2D scanning.

* [RF Drivers](https://goochandhousego.com/product-categories/rf-drivers). Dual Driver 97-0600x-yy is qualified	for 2D scanning.

* [AOMC 350-6](https://goochandhousego.com/product-categories/multi-channel-modulators-aomc) 6-channel AOM, $F_c=350\mathrm{MHz}$, TeO2. (This one is ruled out.)

#### Custom
> 95% of our business is custom versions, designed for each specific high volume customer.

### Leysop Ltd.
#### Standard
* [EOD](http://www.leysop.com/eod_q_switch.htm)

但确实就是想要有大偏转很难, 1kV的驱动只能偏转几mrad.

## 进展
* 2018.3.8 Gooch & Housego 的两支一维AOD到货.
参数见 [97-03283-01](https://github.com/iontrapnet/Jun_Wang/blob/master/%E8%B4%AD%E7%BD%AE/GoochHousegoAOD/97-03283-01%C2%A0Rev%C2%A0B.pdf), 厂家提供的偏转角与RF频率的关系如 [图](https://github.com/iontrapnet/Jun_Wang/blob/master/%E8%B4%AD%E7%BD%AE/GoochHousegoAOD/diffractionAngelVS.Frequency(97-03283-01).png) , 另有纸版出厂测试data sheet在302.

* 3月下旬, 检验了单只AOD的衍射效率, 370nm最高到88%, 399nm最高到92% (感谢李博文). 检验了偏转范围: 100~120MHz约1mrad, 与厂家描述一致.
* 4.1 尝试两AOD级联补偿消频移, 实现了沿45$^\circ$角分线方向偏转370nm. 频移是否因此抵消尚未检验.

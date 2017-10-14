---
layout: szhang_note
category: notes
math: true
title: AOD Investigation
---

## How Nigg used AOM:

0. shift laser frequency
1. in Laser locking system: "noise eater", high bandwidth frequency control
2. shift laser frequency of the $\sigma_+$ & \(\pi\) in Raman Operation


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
 	- **deflection range is limited** to $3\sim 5 \mathrm{rad/kV}$ 

### OD qualification:
* deflection range $\Delta \phi = \lambda \Delta f/v_a$ -- $\Delta f$ ~ AO bandwidth; $v_a$ ~ acoustic wave velocity
	* rf.vl. $\mathrm{RF:} f_0=70\mathrm{MHz}, \Delta f=40\mathrm{MHz}, \Delta \phi=47\mathrm{mrad}$
* number of resovable spots $N = \frac{\pi}{4}\frac{D\Delta f}{v_a}$
* switching speed: just acoustic transit time $\tau_a = D/v_a$. 
	 - low enough to avoid motional heat during ion transport
	 - high enought to allow arbitrary addressing
* focus position resolution , rf.vl. $3.79\mu \mathrm{m/MHz}$
* 1st order diffraction efficiency, rf.vl. At $633\mathrm{nm}$ for $0.7\mathrm{W}$ RF, plateau of $92%$ over $\pm 10\mathrm{MHz}$ around $f_0$ with a fall-off to $\sim 72%$ at the $\pm 20\mathrm{MHz}$ band edges.


## Kumph thesis *2D Arrays of Ion Traps for Large Scale Integration of Quantum Information Processors*:
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
* [AOBD-UV 3246 or 3283](https://goochandhousego.com/wp-content/uploads/2016/04/GH-AO-UV-Beam-Deflector.pdf)
	* Both of them work on 355nm and have 1% insertion loss.
	* The major difference between 3246 and 3283 is RF bandwidth, and thus scan angle. In order to cover a $40\mu\mathrm{m}$ range,
		* 3246: 4.9mrad ~ distance=8.2mm
		* 3283: 1.2mrad ~ distance=33mm
* [AOMC 350-6](https://goochandhousego.com/product-categories/multi-channel-modulators-aomc) 6-channel AOM, $F_c=350\mathrm{MHz}$, TeO2

#### Custom
> 95% of our business is custom versions, designed for each specific high volume customer.
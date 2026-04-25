---
title: 'Nutrition'
date: 2024-12-30
permalink: /posts/2024/08/nutrition/
tags:
  - Nutrition
---
<!-- MathJax -->
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$', '$$'], ['\\[', '\\]']],
      processEscapes: true
    }
  });
</script>
<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.3/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

These are notes on nutrition from a biochemistry and physiology point of view. The goal is not to make a diet plan, but to understand the major categories of nutrients and the basic logic by which the body stores energy, transports lipids, uses vitamins, and regulates water and pH.

# Carbohydrates

Carbohydrates are molecules made primarily of carbon, hydrogen, and oxygen. Their simplest role is energy, but they also appear in structural molecules, nucleic acids, glycoproteins, and cell-surface recognition.

The basic categories are:

* Monosaccharides: glucose, fructose, galactose.
* Disaccharides: sucrose, lactose, maltose.
* Polysaccharides: starch, glycogen, fiber.

Glucose is the main circulating carbohydrate fuel. Cells can oxidize glucose through glycolysis and the citric acid cycle to produce ATP. When glucose is abundant, animals store it as glycogen, especially in liver and skeletal muscle.

Starch and glycogen are digestible polysaccharides made of glucose units. Fiber is different: humans cannot digest many dietary fibers into glucose because we lack the enzymes needed to break their chemical bonds. This does not make fiber useless. It changes digestion, slows glucose absorption, feeds gut microbes, and contributes to stool bulk.

The body maintains blood glucose in a relatively narrow range. Insulin promotes glucose uptake and storage after meals. Glucagon promotes glucose release from liver glycogen and glucose production during fasting.

# Lipids

Lipids are hydrophobic or amphipathic molecules. They are useful precisely because they do not mix easily with water: they form membranes, store dense energy, and act as precursors for signaling molecules.

Important lipid classes:

* Triglycerides: glycerol plus three fatty acids. These are the main storage form of fat.
* Phospholipids: amphipathic lipids that form cell membranes.
* Sterols: cholesterol and cholesterol-derived molecules such as bile acids, steroid hormones, and vitamin D.

Triglycerides are energy-dense because fatty acids are highly reduced. Oxidizing fatty acids yields more ATP per gram than oxidizing carbohydrates or proteins. This is why adipose tissue is an efficient long-term energy store.

Fatty acids differ by saturation:

* Saturated fatty acids have no carbon-carbon double bonds.
* Monounsaturated fatty acids have one double bond.
* Polyunsaturated fatty acids have more than one double bond.
* Trans fats are unsaturated fats with at least one trans double bond.

The geometry matters. Cis double bonds introduce bends into fatty acid chains and change membrane fluidity. Trans fats behave more like saturated fats structurally, and industrial trans fats are particularly unfavorable for cardiovascular risk.

# Lipid Transport

Because lipids do not dissolve well in blood, the body packages them into lipoproteins. A lipoprotein is a transport particle made of lipids and proteins. The surface contains phospholipids, free cholesterol, and apolipoproteins; the interior carries hydrophobic cargo such as triglycerides and cholesteryl esters.

The major lipoproteins are:

* Chylomicrons: transport dietary triglycerides from the intestine.
* VLDL: transport triglycerides made by the liver.
* LDL: deliver cholesterol-rich particles to tissues.
* HDL: participate in reverse cholesterol transport, moving cholesterol away from tissues toward the liver.

A common simplification is "LDL is bad and HDL is good." This is useful as a first mnemonic, but biologically incomplete. LDL is necessary for lipid transport, but elevated LDL cholesterol is associated with atherosclerotic cardiovascular disease. HDL participates in cholesterol efflux, but simply raising HDL is not automatically protective; the whole lipid and metabolic context matters.

A standard lipid panel directly measures or reports:

* Total cholesterol.
* HDL cholesterol.
* Triglycerides.
* LDL cholesterol, either directly measured or estimated.

The traditional Friedewald estimate, when values are in mg/dL, is

$$
\mathrm{LDL}\text{-}C
= \mathrm{Total\ cholesterol}
- \mathrm{HDL}\text{-}C
- \frac{\mathrm{Triglycerides}}{5}.
$$

The term $\mathrm{Triglycerides}/5$ estimates VLDL cholesterol. This approximation is less reliable when triglycerides are high, and many laboratories now use newer LDL estimation methods or direct LDL measurement in some settings.

Dietary fats affect blood lipids differently. Saturated fat tends to raise LDL cholesterol. Trans fats tend to raise LDL and lower HDL, which is why they are considered especially harmful. Unsaturated fats, especially when they replace saturated or trans fats, are generally more favorable for blood lipid profiles.

# Protein

Proteins are polymers of amino acids. They are not just "muscle nutrients"; proteins form enzymes, receptors, transporters, antibodies, structural fibers, and signaling molecules.

There are twenty common amino acids used in human proteins. Some are essential, meaning the body cannot synthesize enough of them and they must come from the diet. Protein digestion breaks dietary proteins into amino acids and short peptides, which are absorbed and reused.

Protein can be used for energy, but that is not its most elegant role. Unlike fat and carbohydrate, protein contains nitrogen. When amino acids are broken down, their nitrogen must be handled safely, primarily through conversion to urea and excretion by the kidneys.

# Vitamins

Vitamins are organic compounds required in small amounts for normal metabolism. They often act as enzyme cofactors or precursors to cofactors.

The key distinction is solubility.

Water-soluble vitamins:

* Vitamin C.
* B vitamins.

These are generally not stored in large amounts, and excess is often excreted in urine. This means deficiency can appear relatively quickly if intake or absorption is poor.

Fat-soluble vitamins:

* Vitamin A.
* Vitamin D.
* Vitamin E.
* Vitamin K.

These require normal fat absorption and can be stored in the body. Because they are stored more readily, excessive supplementation can be risky, especially for vitamins A and D.

# B Vitamins

B vitamins are central to metabolism because many become coenzymes. A coenzyme helps an enzyme perform a chemical reaction.

Some important examples:

* Thiamine, vitamin B1: precursor to thiamine pyrophosphate (TPP), important in carbohydrate metabolism.
* Riboflavin, vitamin B2: precursor to FAD and FMN, used in redox reactions.
* Niacin, vitamin B3: precursor to NAD and NADP, used in redox metabolism.
* Pantothenic acid, vitamin B5: part of coenzyme A.
* Pyridoxine, vitamin B6: precursor to PLP, important in amino acid metabolism.
* Biotin, vitamin B7: cofactor for carboxylation reactions.
* Folate, vitamin B9: involved in one-carbon metabolism and nucleotide synthesis.
* Cobalamin, vitamin B12: involved in methylation reactions and red blood cell formation.

B12 is found naturally in animal-derived foods, which is why people eating fully plant-based diets usually need fortified foods or supplements. Folate and B12 are closely linked in one-carbon metabolism, so deficiency in either can affect DNA synthesis and red blood cell production.

Vitamin B6 is water-soluble, but very high supplemental intakes can still cause toxicity, especially neuropathy. "Water-soluble" does not mean "impossible to overdo."

# Vitamin C

Vitamin C, or ascorbic acid, is water-soluble. It acts as a reducing agent and antioxidant, but one of its most important roles is in collagen synthesis.

Collagen contains modified amino acids such as hydroxyproline and hydroxylysine. Vitamin C is required for the hydroxylation reactions that make stable collagen possible. Severe vitamin C deficiency causes scurvy, where weakened collagen leads to symptoms such as bleeding gums, poor wound healing, and fragile connective tissue.

Vitamin C also helps keep iron in a reduced form that is easier to absorb, which is why vitamin C can improve absorption of non-heme iron from plant foods.

# Minerals and Electrolytes

Minerals are inorganic nutrients. Some are required in larger amounts, such as calcium, phosphorus, magnesium, sodium, potassium, and chloride. Others are trace minerals, such as iron, zinc, iodine, selenium, copper, and manganese.

Electrolytes are ions that affect fluid balance, nerve conduction, muscle contraction, and acid-base physiology. The most important ones to keep straight are:

* Sodium: major extracellular cation.
* Potassium: major intracellular cation.
* Chloride: major extracellular anion.
* Bicarbonate: important buffer.
* Calcium: signaling, muscle contraction, bone structure.
* Magnesium: enzyme function and ATP-related chemistry.

Sodium and potassium are especially important for electrical excitability. Neurons and muscle cells rely on ion gradients across membranes. The sodium-potassium pump maintains these gradients by using ATP to move sodium out of cells and potassium into cells.

# Water

Water is the solvent in which most physiology happens. It gives blood its volume, allows solutes to move, participates in temperature regulation, and provides the medium for biochemical reactions.

Hard water contains more calcium and magnesium. Soft water contains fewer divalent minerals and may contain more sodium depending on how it was softened. Hard water is not automatically "good" and soft water is not automatically "bad"; the practical significance depends on mineral content, sodium content, taste, plumbing, and individual health considerations.

Fluid regulation is tightly connected to sodium:

$$
\text{sodium balance}
\longrightarrow \text{water retention}
\longrightarrow \text{blood volume}
\longrightarrow \text{blood pressure}.
$$

The body regulates water through thirst, kidney function, antidiuretic hormone (ADH), aldosterone, and natriuretic peptides. In broad strokes:

* ADH promotes water reabsorption in the kidneys.
* Aldosterone promotes sodium reabsorption, with water often following sodium.
* Natriuretic peptides promote sodium and water excretion when blood volume is high.

# Acid-Base Balance

Blood pH is normally slightly basic, roughly $7.35$ to $7.45$. The body keeps it close to this range because protein structure, enzyme activity, oxygen binding, and ion channel behavior all depend on pH.

The most important buffer system in blood is the bicarbonate buffer:

$$
\mathrm{CO_2 + H_2O \rightleftharpoons H_2CO_3
\rightleftharpoons H^+ + HCO_3^-}.
$$

Carbon dioxide behaves as the respiratory component of this buffer system because the lungs can remove $\mathrm{CO_2}$. Bicarbonate behaves as the metabolic or renal component because the kidneys can regulate $\mathrm{HCO_3^-}$ and hydrogen ion excretion.

The Henderson-Hasselbalch equation is

$$
\mathrm{pH} = \mathrm{p}K_a + \log_{10}\left(\frac{[\mathrm{A^-}]}{[\mathrm{HA}]}\right).
$$

For the bicarbonate system in blood, a common physiological form is

$$
\mathrm{pH} = 6.1 + \log_{10}
\left(
\frac{[\mathrm{HCO_3^-}]}
{0.03\,P_{\mathrm{CO_2}}}
\right).
$$

This equation explains why both lungs and kidneys matter:

* If ventilation decreases, $\mathrm{CO_2}$ rises and pH falls.
* If ventilation increases, $\mathrm{CO_2}$ falls and pH rises.
* If bicarbonate falls, pH falls.
* If bicarbonate rises, pH rises.

So acid-base regulation is not just chemistry in a beaker. It is chemistry plus breathing plus kidney physiology.

# A Useful Mental Model

A compact way to organize nutrition is:

* Carbohydrates: fast and stored glucose energy.
* Lipids: dense energy storage, membranes, and lipid signaling.
* Proteins: structure, enzymes, transport, signaling, and repair.
* Vitamins: organic helpers for metabolic reactions.
* Minerals: inorganic structure, charge balance, and enzyme support.
* Water: solvent, transport medium, temperature regulator, and volume regulator.

The body is not simply "burning calories." It is maintaining gradients, building structures, moving information, defending pH, and deciding when to store or release energy.

# References

* [American Heart Association: Saturated Fats](https://www.heart.org/en/healthy-living/healthy-eating/eat-smart/fats/saturated-fats)
* [American Heart Association: Understanding Cholesterol and Lipids](https://www.heart.org/en/health-topics/cholesterol/your-complete-guide-to-understanding-cholesterol-and-lipids)
* [Johns Hopkins Medicine: Calculating Your Cholesterol](https://www.hopkinsmedicine.org/health/wellness-and-prevention/calculating-your-cholesterol)
* [Merck Manual: Overview of Acid-Base Balance](https://www.merckmanuals.com/home/hormonal-and-metabolic-disorders/acid-base-balance/overview-of-acid-base-balance)

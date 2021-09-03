3 Models predicting labels by using news Titles in Turkish Language

The models in that study are based on distribution of stems of words in title of news. 
In doing so, we have some problems, to be tackled meticulously , and their answers shown below

1) Which words in title of news must be selected? all ? or some?

Answer:
all but prepositions, exclamations and preferably two or three letter words (due to large size of semantic scope and thereby causing biased prediction)

2) Turkish is agglutinating language. So semantic difference between word and stem may be high.
Then what is true stem of the word ? 

Answer:
the best stem to be chosen may be supposed to be the stem with maximum size in the word, if possible, but not itself  
 
Explanation:

For example: Let's deal with the word "Gözlükçüler" (Opticians),
First of all, this word is in plural form, it should be reduced into singular form, gözlükçü (optician)

Stem to word hierarchy:

Göz (eye)
Gözlük (eyeglass)
Gözlükçü (optician)

Here Göz (eye) is the basic stem with minimum length. But semantic difference between göz (eye) and gözlük (eyeglass) are larger than 
the semantic difference between gözlük (eyeglass) and gözlükçü (optician). Because semantic scope of göz (eye) is much larger than of gözlükçü (optician).

Herein  which stem should we should pick for "Gözlükçüler(opticians)"? Göz (eye) ? Gözlük (eyeglass) ? Gözlükçü (optician) ?

Due to vast size of its semantic scope, all sentences (or documents) including göz (eye) may not be semantically related to Gözlükçüler(opticians).
Likewise if we choose Gözlükçü (optician), then semantic scope will be confined into the word rather than stem.
Then in this context Gözlük (eyeglass) is the best stem to involve semantic scope of Gözlükçüler(opticians). 
Because all sentences (or documents) including Gözlük (eyeglass) is semantically related to Gözlükçüler (opticians) somehow.

3) How to tackle "Final-obstruent devoicing" problem in Turkis language when determining true stem ?

Answer: 
Firstly, let's explain "Final-obstruent devoicing": if a word ending with consonant "p,ç,t,k" takes suffix beginning with vowel, then ending consonant of the word transforms into "b,c,d,g,ð (for k)". 
But practically "g" is not used usually. Then stem of the word is deformed. 
Example: 
"kitap"(book) +"-ým" (my-suffix indicating 1st singular possesive)="kitabým" (my book)
"aðaç"(tree)+"-a" (to-Dativ case)="aðaca"(to the tree)
"umut"(hope)+"-un" (your-suffix indicating 2st singular possesive)="umudun" (your hope)
"ekmek"(bread)+"-e" (to-Dativ case)="ekmeðe"(to the bread)

In order to overcome that problem, I developed an algorithm to detect that case and to reconstruct deformed stem. 

4) Another problem: designed process in "1stStep_turkish_stems.ipynb" does not give real stem. 
This can be problem ?
Answer:
Not exactly, 
because For example, it gives "umu" (the thing that is hoped-used very rarely) as stem with maximum length of the word "umudun" (...of hope).
and let's look at the stems starting with "umu" in stem_list: (1stStep_turkish_stems.ipynb
umu-umut-umum-umumhane-umumi-umumiyet-umur-umural-umuralp-umurbay-umurbey-umursa-umursamaz-umursamazca

It is obivous that words beginning with "umut" (hope) and "umud" ( "Final-obstruent devoicing" form) are got connected with just "umu",
but other versions, words beginning with "umum" (public) and "umur" (care in noun form-used very rarely) are got connected with "umur" and "umum",respectively.
In this respect, different meanings are connected with different stems.
However some exceptions may cause problem in minor scale.



 
  

  








  
# Week 5 Lab Report
By: Jonathan Nguyen
PID: A17418793 <br>
# Part 1 - Bugs

Bug chosen: bug in ``ArrayExamples.java`` in the ``reversed`` method

A failure-inducing input for the buggy program:
```
@Test
public void testReversed2() {
  int[] input1 = {1, 2, 3};
  assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
}
```
The symptom: <br> ![Image](https://i.imgur.com/kArZdAV.png)

An input that does not cause a failure:
```
@Test
public void testReversed2() {
  int[] input1 = {0, 0, 0};
  assertArrayEquals(new int[]{0, 0, 0}, ArrayExamples.reversed(input1));
}
```
The symptom: <br> ![Image](https://i.imgur.com/Zaj8bBM.png)

The bug: 
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```

The fixed code:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```

My reasoning for the bugfix:

The programmer was affecting the input array instead of the initialized array and additionally returned the wrong array. Grabbing values in reverse from a initialized array will not reverse the array. 


# Part 2 - Researching Commands

##Chosen command: ``less``

### The argument: ``-N`` 
### Example 1: <br>
The directory: ``~/Downloads/docsearch/`` <br>
The command: ``less -N biomed-sizes.txt`` <br>
Output: <br> 
```
      1      432     3380    24544 technical/biomed/1468-6708-3-1.txt
      2      533     3630    30118 technical/biomed/1468-6708-3-10.txt
      3      296     2166    17178 technical/biomed/1468-6708-3-3.txt
      4      547     4301    31925 technical/biomed/1468-6708-3-4.txt
      5      317     2312    18431 technical/biomed/1468-6708-3-7.txt
      6      411     3181    24439 technical/biomed/1471-2091-2-10.txt
      7      615     4684    35718 technical/biomed/1471-2091-2-11.txt
      8      515     3287    25366 technical/biomed/1471-2091-2-12.txt
      9      564     3550    28534 technical/biomed/1471-2091-2-13.txt
     10      339     2496    19055 technical/biomed/1471-2091-2-16.txt
     11      826     5832    46240 technical/biomed/1471-2091-2-5.txt
     12      501     3167    25959 technical/biomed/1471-2091-2-7.txt
     13      481     3637    25779 technical/biomed/1471-2091-2-9.txt
     14      537     4002    29676 technical/biomed/1471-2091-3-13.txt
     15      932     7125    55781 technical/biomed/1471-2091-3-14.txt
     16      673     4858    34882 technical/biomed/1471-2091-3-15.txt
     17      702     5011    36655 technical/biomed/1471-2091-3-16.txt
     18      642     4251    30111 technical/biomed/1471-2091-3-17.txt
     19      708     5587    41266 technical/biomed/1471-2091-3-18.txt
     20      755     5001    41134 technical/biomed/1471-2091-3-22.txt
     21      605     4616    34420 technical/biomed/1471-2091-3-23.txt
     22      699     4531    34867 technical/biomed/1471-2091-3-30.txt
     23     1063     7146    57063 technical/biomed/1471-2091-3-31.txt
     24     1013     7118    53710 technical/biomed/1471-2091-3-4.txt
     25      430     3136    23921 technical/biomed/1471-2091-3-8.txt
     26      545     3908    30824 technical/biomed/1471-2091-4-1.txt
     27      521     3765    29240 technical/biomed/1471-2091-4-5.txt
     28      784     4587    37372 technical/biomed/1471-2105-1-1.txt
     29      611     4414    34872 technical/biomed/1471-2105-2-1.txt
     30     1495     8652    69647 technical/biomed/1471-2105-2-8.txt
     31      455     3425    26087 technical/biomed/1471-2105-2-9.txt
     32      393     2665    21467 technical/biomed/1471-2105-3-12.txt
     33     1173     6982    55614 technical/biomed/1471-2105-3-14.txt
     34      776     4989    38222 technical/biomed/1471-2105-3-16.txt
     35      920     5988    48159 technical/biomed/1471-2105-3-17.txt
     36     2236     9393    80798 technical/biomed/1471-2105-3-18.txt
```
<br>
Explanation: It output a column of line numbers on the left hand side. I expect this to be helpful if the file was sorted in some meaningful order. <br>

### Example 2: <br>

The directory: ``~/Downloads/docsearch/technical/biomed`` <br>
The command: ``less -N gb-2003-4-9-r60.txt`` <br>
Output: <br> 
```
      1
      2
      3
      4
      5         Rationale
      6         The post-genomic era has introduced high-throughput
      7         methodologies that generate experimental data at rates that
      8         exceed knowledge growth. In particular, high-density
      9         biochips including complementary deoxyribonucleic acid
     10         (cDNA) microarrays, oligonucleotide microarrays, and
     11         rapidly evolving proteomics platforms represent modern
     12         tools able to interrogate biology on a genome-wide scale
     13         and generate tens of thousands of data points
     14         simultaneously [ 1 ] . While researchers are beginning to
     15         appreciate the statistical rigors required for the analysis
     16         of genome-scale datasets, a rate-limiting step in knowledge
     17         growth occurs at the transition from statistical
     18         significance to biological discovery.
     19         A number of public efforts are currently focusing on the
     20         annotation and curation of gene-specific functional data,
     21         including LocusLink, Protein Information Resource (PIR),
     22         GeneCards, Proteome, Kyoto Encyclopedia of Genes and
     23         Genomes (KEGG), Ensembl, and Swiss-Prot to name but a few [
     24         2 3 4 5 6 7 8 ] . These resources provide exceptional depth
     25         and coverage of the functional data available for a given
     26         gene, but are not designed to effectively explore the
     27         biological knowledge associated with hundreds or thousands
     28         of genes in parallel. In order to facilitate the functional
     29         annotation and analysis of large lists of genes we have
     30         developed a Database for Annotation, Visualization, and
     31         Integrated Discovery (DAVID), which provides a set of
     32         data-mining tools that systematically combine functionally
     33         descriptive data with intuitive graphical displays [ 9 ] .
     34         DAVID provides exploratory visualization tools that promote
     35         discovery through functional classification, biochemical
     36         pathway maps, and conserved protein domain architectures,
```
<br>
Explanation: It output a column of line numbers on the left hand side. I expect this to be helpful if the file was sorted in some meaningful order. <br>

### The argument: ``-w``
### Example 1: <br>
The directory: ``~/Downloads/docsearch/technical/government/media`` <br>
The command: ``less -w Law_Schools.txt`` <br>
Output: <br>
```
their own, all with an eye toward charging no more than their
clients can afford.
This is not pro bono legal work; it is "low bono," a term the
schools coined to define the atypical kind of law career they are
training students for. While its practitioners do charge for their
services, they are also dead set on turning no one away - or at
least as few as possible.
"When you go into this kind of social justice law, it's really
brutal and you're almost guaranteed to struggle for a couple of
years before there's a light at the end of the tunnel," said Fred
Rooney, director of the Community Legal Resource Network at City
University of New York School of Law, from which the lawyers of the
newly formed Cates, Katalinic & Lund graduated last May. "But
if our graduates don't do it, the millions of people who cannot
access justice in this country will continue to soar."
The movement, primly called the consortium, started four years
ago by CUNY, Northeastern University, the University of Maryland
and St. Mary's Law School in Texas. (St. Mary's later dropped out.)
Since then, it has drawn seven additional law schools to its ranks:
the University of Michigan, Rutgers and Syracuse Law Schools, New
York Law School, University of New Mexico School of Law, Thomas M.
Cooley Law School and Touro Law School. It has elicited at least
initial interest from 19 more. Mixing foundation money with their
own to go beyond the standard curriculum, the schools are teaching
the nuts and bolts of running a business, setting up client
referral networks for fledgling practitioners and holding seminars
to tackle the mundane cha llenges of going it alone that are often
considered superfluous to the study of law.
As further encouragement for the 200 or so followers they have
picked up already, the consortium schools have given their
graduates Palm organizers, paid for companies to help with their
billing, and offered free legal research and even yoga and
meditation classes, almost anything to help make life a little
easier for those trying to hang out their shingles.
"We're talking about training real community lawyers," said Stua
rt L. Deutsch, dean of the Rutgers School of Law in Newark. "The
perception is that the solo practitioners are the ones who got C's,
the second string who didn't excel enough to get to the big firms.
We're trying to say that solo practice can be among the highest
forms of public service, and is the only channel possible to
serving low-income people."
True or not, there is little debate that most low-income
clients, and many in the middle class, find lawyers well outside
their financial reach. Even at the smallest of firms, the median
hourly rate starts at roughly $130 an hour and passes $180,
```
Note that the line `years before there's a light at the end of the tunnel," said Fred` is intended to be highlighted. This line was previously at the bottom of the screen before a scroll.

<br>
Explanation: It highlights the line previously at the bottom when scrolling. It seems to mostly be an accessibility thing, and I quite like it. <br>

### Example 2: <br>

The directory: ``~/Downloads/docsearch/technical/biomed`` <br>
The command: ``less -w gb-2003-4-9-r60.txt`` <br>
Output:<br> 
```
        of genes in parallel. In order to facilitate the functional
        annotation and analysis of large lists of genes we have
        developed a Database for Annotation, Visualization, and
        Integrated Discovery (DAVID), which provides a set of
        data-mining tools that systematically combine functionally
        descriptive data with intuitive graphical displays [ 9 ] .
        DAVID provides exploratory visualization tools that promote
        discovery through functional classification, biochemical
        pathway maps, and conserved protein domain architectures,
        while simultaneously remaining linked to rich sources of
        biological annotation. DAVID expedites the functional
        annotation and analysis of any list of genes encoded by
        human, mouse, rat, or fly genomes. DAVID's functionality is
        demonstrated using the Affymetrix GeneChip data of Cicala
        et al . [ 10 ] .


        System architecture and maintenance

          Analysis modules
          DAVID is composed of four main modules: Annotation
          Tool, GoCharts, KeggCharts, and DomainCharts. The
          Annotation Tool is an automated method for the functional
          annotation of gene lists. Any combination of annotation
          data can be chosen from 10 options by selecting the
          appropriate checkboxes (Table 2). The annotations are
          added to the submitted gene list by selecting the upload
          button, which returns an HTML table containing the user's
          original list of identifiers appended with the chosen
          functional annotations. Unannotated genes are included in
          the output with no appended data for tracking
          purposes.
          The GoCharts module graphically displays the
          distribution of differentially expressed genes among
          functional categories using the controlled vocabulary of
          the Gene Ontology Consortium (GO), which provides a
          structured language that can be applied to the functions
          of genes and proteins in all organisms even as knowledge
          continues to accumulate and change [ 13 ] . The language
          is structured in a directed acyclic graph (DAG), wherein
          term specificity increases and genome coverage decreases
          as one moves down the hierarchy. In contrast with a true
          hierarchy, child terms in a DAG may have more than one
          parent term and may have a different class of
          relationship with its different parents. The structure of
```
Note that the line `while simultaneously remaining linked to rich sources of` is intended to be highlighted. This line was previously at the bottom of the screen before a scroll.
<br>
Explanation: It highlights the line previously at the bottom when scrolling. It seems to mostly be an accessibility thing, and I quite like it. <br>

### The argument: ``--window=n``
### Example 1: <br>
The directory: ``~/Downloads/docsearch/technical/government/media`` <br>
The command: ``less --window=1 -w Law_Schools.txt`` <br>
Output:<br>
```
clients can afford.
This is not pro bono legal work; it is "low bono," a term the
schools coined to define the atypical kind of law career they are
training students for. While its practitioners do charge for their
services, they are also dead set on turning no one away - or at
least as few as possible.
"When you go into this kind of social justice law, it's really
brutal and you're almost guaranteed to struggle for a couple of
years before there's a light at the end of the tunnel," said Fred
Rooney, director of the Community Legal Resource Network at City
```

```
This is not pro bono legal work; it is "low bono," a term the
schools coined to define the atypical kind of law career they are
training students for. While its practitioners do charge for their
services, they are also dead set on turning no one away - or at
least as few as possible.
"When you go into this kind of social justice law, it's really
brutal and you're almost guaranteed to struggle for a couple of
years before there's a light at the end of the tunnel," said Fred
Rooney, director of the Community Legal Resource Network at City
University of New York School of Law, from which the lawyers of the
```
In the second output block, the highlighted line is `University of New York School of Law, from which the lawyers of the`. We learned that the -w argument will highlight the previous line at the bottom, so we know that the argument --window=1 will change the scroll setting to 1 line.
<br>
Explanation: It changes the default scroll setting to be in n lines, in this case I wanted it to scroll only 1 line when I clicked space. It is useful if your reading style varies from the default setting. <br>

### Example 2: <br>

The directory: ``~/Downloads/docsearch/technical/plos`` <br>
The command: ``less --window=3 -w pmed.0020201.txt`` <br>
Output: 
```
In this month's
        PLoS Medicine , Lorenz Studer and colleagues from the Sloan-Kettering
        Institute in New York describe a protocol for deriving mesenchymal precursors, which they
        then show are capable of differentiating into specialized cell types.
        They used two undifferentiated stem cell lines—from the 22 lines that were approved in
        2001 by President Bush for use in federally funded research in the United States. The
        specifications for approval for these lines are clear—see the guidelines at
        http://stemcells.nih.gov/research/registry/eligibilityCriteria.asp. The number of human
        embryonic stem cell lines available for researchers are strictly limited, making it
        necessary to develop protocols that expand these cells along various lineages.
        In order to differentiate the cells into mesenchymal precursors, the stem cell lines
        were cocultured with mouse feeder cells to produce five different polyclonal lines. The
        authors then cultured these polyclonal precursors with appropriate tissue-specific
        stimulation in attempt to produce fat, bone, cartilage, or muscle cells. The evidence that
        the authors provide for these cells being differentiated includes analysis of gene
        expression, surface antigens, and immunocytochemistry typical of the mature tissues. For
        example, the authors were able to show the presence of fat granules in adipocytes, calcium
        in the matrix of osteogenic cells, and collagen in chondrocytes. It was harder to produce
        muscle cells, but even these types of cells could eventually be induced by specific culture
        conditions.
        What are the possible concerns about these types of studies? One obvious one is the
        potential for residual undifferentiated cells to turn into tumors, but the authors tested
        the differentiated cell cultures for cell surface markers characteristic of
        undifferentiated cells and found no evidence of them. Another worry for the use of these
```

```
In this month's
        PLoS Medicine , Lorenz Studer and colleagues from the Sloan-Kettering
        Institute in New York describe a protocol for deriving mesenchymal precursors, which they
        then show are capable of differentiating into specialized cell types.
        They used two undifferentiated stem cell lines—from the 22 lines that were approved in
        2001 by President Bush for use in federally funded research in the United States. The
        specifications for approval for these lines are clear—see the guidelines at
        http://stemcells.nih.gov/research/registry/eligibilityCriteria.asp. The number of human
        embryonic stem cell lines available for researchers are strictly limited, making it
        necessary to develop protocols that expand these cells along various lineages.
        In order to differentiate the cells into mesenchymal precursors, the stem cell lines
        were cocultured with mouse feeder cells to produce five different polyclonal lines. The
        authors then cultured these polyclonal precursors with appropriate tissue-specific
        stimulation in attempt to produce fat, bone, cartilage, or muscle cells. The evidence that
        the authors provide for these cells being differentiated includes analysis of gene
        expression, surface antigens, and immunocytochemistry typical of the mature tissues. For
        example, the authors were able to show the presence of fat granules in adipocytes, calcium
        in the matrix of osteogenic cells, and collagen in chondrocytes. It was harder to produce
        muscle cells, but even these types of cells could eventually be induced by specific culture
        conditions.
        What are the possible concerns about these types of studies? One obvious one is the
        potential for residual undifferentiated cells to turn into tumors, but the authors tested
        the differentiated cell cultures for cell surface markers characteristic of
        undifferentiated cells and found no evidence of them. Another worry for the use of these
        cells directly in humans is the need, at least at the beginning, to culture the cells with
        mouse feeder cells—obviously no human treatment could contain cells contaminated with mouse
        cells. Further development of protocols will be needed to address this issue. However, as
```
In the second output block, the highlighted line is `cells directly in humans is the need, at least at the beginning, to culture the cells with`. We learned that the -w argument will highlight the previous line at the bottom, so we know that the argument --window=3 will change the scroll setting to 3 line.
<br>
Explanation: It changes the default scroll setting to be in n lines, in this case I wanted it to scroll only 1 line when I clicked space. It is useful if your reading style varies from the default setting.

### The argument: ``-f`` <br>
### Example 1: <br>
The directory: ``~/Downloads/docsearch`` <br>
The command: ``less -f lib`` <br>
Output:<br> 
```




































lib (END)
```

<br>
Explanation: It forces a file to be opened by the less command, whether or not it is allowed by default. In this case, using it on a directory output nothing, which makes sense to me. <br>
## Example 2: <br>
The directory: ``~/Downloads/docsearch/technical/government/About_LSC`` <br>
The command: ``less -f conference_highlights.txt`` <br>
Output:<br> 

```
A CONFERENCE OF STATEWIDE PROGRAMS
February 8 - 9, 2002


Indianapolis, Indiana
Introduction
In the summer of 2001, LSC's State Planning Team determined that
there is a critical need to communicate clearly the key elements of
planning related to statewide legal services programs. The Team
suggested a national initiative to bring together executive
directors of statewide programs around the state planning agenda.
The goal was to focus executive directors on the fundamentals of
planning for client-centered, comprehensive, integrated statewide
justice communities. This initiative was specifically designed to
bring together executive leadership from newly created statewide
LSC-funded programs and the experienced leadership of the more
historical statewide programs. This peer group benefited from the
opportunity to come together to discuss the challenges and new
opportunities created by the processes of state planning.


Background
This meeting was originally scheduled for September 13 - 15,
2001, but was postponed in the aftermath of the September 11th
attack on the U.S.
LSC staff planned and coordinated this conference, and the
Corporation sponsored the participation of executive directors by
covering their travel costs. Additionally, programs were offered
the option of sending additional staff to the conference at their
own expense. Amidst a professional and amiable backdrop, the
conference was convened at the Marriott Hotel in downtown
Indianapolis, Indiana. A total of 31 program representatives
```

<br>
Explanation: -f forces a file to be opened regardless if it can or not, but if used on a normal .txt file then it appears to just open it normally.


Cited source: https://linux.die.net/man/1/less


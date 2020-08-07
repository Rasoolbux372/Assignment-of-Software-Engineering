# Assignment-of-Software-Engineering

## Q.No.01:

### Improved Automatic Summarization of Subroutines via Attention to File Context

# summary:

# Arthur : 

### Sakib Haque , Alexander LeClair , Lingfei Wu , Collin McMillan 

# Conference : 

### In 17th International Conference on Mining Software Repositories (MSR ’20), October 5–6, 2020, Seoul, Republic of Korea

### INTRODUCTION : 

#### One of the most important aspects of software documentation is the generation of short, usually one-sentence, descriptions of the subroutines in the software source code. The task of generating these descriptions has become known as «summarization» of subroutines. Yet while currently a vast majority of summarization is handled manually by a programmer, automatic summarization has a long history of scientific interest and been described as a «holy grail» of SE research. A flurry of recent research has started to make automatic summarization a reality.
Nearly all of the literature on these AI-based approaches to subroutine summarization is inspired by Neural Machine Translation use an attention mechanism to learn associations between subroutines in the file context to words in the target subroutine’s summary during training. Our idea is novel because existing approaches generally only attend words in the output summary to words in the target subroutine. In our experimental section, we demonstrate that our approach improves existing baselines by providing orthogonal information to help the model provide better predictions for otherwise difficult to understand subroutines.

# Methodology : 

### we follow the methodology established by many papers on code summarization in both SE and machine translation in NLP. We obtain a standard dataset , then use several baselines plus our approach to create predictions on the dataset, then compute quantitative metrics for the output. The quantitative metrics we use are BLEU and ROUGE . These two metrics have various advantages and disadvantages, but one or another form the foundation of nearly all experiments on neural-based translation or summarization.In cases when the reference is only three words long we calculate onlyFirst, we provide an overview comparison of predictions by different models to determine whether the inputs give orthogonal results and estimate the proportion of predictions may be helped by file context. Attendgru This baseline represents a «no frills» attentional encoderdecoder model using unidirectional GRUs. We configure attendgru with identical hyperparameters to our approach whenever they overlap . Ast-attendgru This is the approach LeClair et al.
proposed an attention-only machine translation model in 2017. It was received in the NLP community with significant fanfare so, given the success of the model for NMT, we evaluate it as a baseline. proposed using a graph-NN to model source code, but applied it to a code generation task in their implementation. To reproduce the idea as a baseline for code summarization, we use a graph-NN-based text generation system proposed by Xu et al.
described in Section 3.1, is a recent code summarization approach based on AST paths that is reported to have good results on a C# dataset. We reimplemented the approach from Section 3.2 of their paper, with their online implementation as a guide. Note we did not use their implementation verbatim. Otherwise, it would not have been possible to know whether performance differences were due to file context or these other factors.

## Result : 

#### This paper advances the state of the art by demonstrating how file context can be used to improve neural source code summarization. The idea that file context includes important clues for understanding subroutines is well-studied in software engineering and especially program comprehension – it has even been proposed for code summarization . The result is that the model is able to use more words from that context, as in the following examples for maximum reproducibility, number is method ID in the dataset followed by the reference summary, attention visualizations As with all papers, our work carries threats to validity and limitations. For one, we use a quantitative evaluation methodology, which while in line with almost all related work and which enables us to evaluate the approach over tens of thousands of subroutines, may miss nuances that a qualitative human evaluation would catch.
However, space limitations prevent us from including a thorough discussion of both in a single paper, so we defer a human evaluation for extended work. Another limitation is that we evaluate only against a Java dataset. This dataset is the largest available that follows good practice to avoid biases , but caution is advisable when generalizing the work to other languages.

## Q.no.02


### JTeC: A Large Collection of Java Test Classes for Test Code Analysis and Processing

# summary:

## Arthur :

### Federico Corò ,  Roberto Verdecchia , Emilio Cruciani , Breno Miranda , Antonia Bertolino 

# Conference:
### In 17th International Conference on Mining Software Repositories (MSR ’20), October 5–6, 2020, Seoul, Republic of Korea

# Introduction:

### Test computerization has been effectively sought after since the 90's as an answer for lessen the significant expenses of programming testing and improve item quality . Zion Market Research assesses that the product test mechanization market will develop from the 16 Billion Dollars of 2016 up to 55. All the above examination endeavors request accessibility of a huge dataset of test code, to which the proposed techniques and devices can be applied. Anyway there doesn't yet exist such an assortment for prepared use by the network. As we ourselves are going to need such a dataset for approving our versatile way to deal with test prioritization , we might want to make accessible for the use of the network the test classes dataset that we gathered. At the hour of accommodation, the dataset, called JTeC , gives 2.5M+ test classes gathered from a lot of 31K+ tasks in Github, which starting now and into the foreseeable future the network taking a shot at test code investigation and handling can reuse without burning through further energy. 
The JTeC dataset, and the quality sifting content which is given as supplement to the dataset, are accessible online in the JTeC group. In the rest of depict the technique followed to gather the dataset , its structure , and how it very well may be utilized for research . We finish up the paper indicating conceived future JTeC improvements.

# METHODOLOGY:

### The first step of our process consists of indexing the public GitHub repositories, and is carried out in order to execute efficiently the subsequent phases of our process. In this step we first retrieve the name of the public repositories and the username of their creators. This is achieved via a query to the GitHub API3 specifying the unique identifiers of the repositories in an incremental fashion . As stopping criterion for the repository indexing process we adopt the number of repositories required to collect 2.5M test classes.
This number is approximated via a preliminary exploratory analysis, and amounts to approximately 31K repositories. Subsequently, once we obtain the list of repository names mapped to the usernames of their creators, we can launch a second query to the GitHub API in order to retrieve the programming languages associated with each repository. Once obtained a local copy of the indexed repositories mapped to their programming languages, we can effortlessly retrieve the URLs of the repositories developed in a specific language. Csv file created in the previous step to isolate the repositories developed exclusively in Java by inspecting the language tag of the indexed repositories, and subsequently combine their name with the username of their creators in order to identify the unique URL of the repositories.
The final output of this step is the list of URLs corresponding to all Once we isolated the repositories developed in Java, we can identify the test classes of the repositories to store them locally. This is achieved by leveraging the standard naming conventions for Java test classes in Junit, the most popular Java unit testing framework . Specifically, we do this by selecting the source code files of the selected repositories whose name ends with «Test. Java» and «Tests

# Result:

### They have presented the JTeC dataset that makes ready available to the community of software testing researchers a large collection of Java test classes useful for several potential purposes related to test code analysis and processing. Given the large scale, obtaining such information is clearly highly effort-intensive, and we consider that coarse criteria such as function coverage would be enough. Having this type of information could support benchmarking other regression testing techniques beyond black-box similarity-based ones. Additionally, to broaden the capabilities of JTeC, we envision to include in future versions also fault information of the identified test classes.

Providing this latter type of information, would enable researchers to have at disposal a large-scale real-world dataset containing the most important information related to test suites, enabling them to conduct a vast range of studies related to the research field of software testing.


## Q.No.03 

 Ownership at large:
 
 Open Problems and Challenges in Ownership Management 

# summary:

# authurs:

### JohnAhlgren  ,Maria Eugenia Berezin, Kinga Bojarczuk, Elena Dulskyte ,Inna Dvortsova ,Johann   George, Natalija Gucevska, Mark Harman, ShanHe, Ralf Lämmel, ErikMeijer, Silvia Sapora, and Justin Spahr -Summers∗ FacebookInc.

# Conference:

## This paper appears in Proceedings of 28th International Conference on Program Comprehension,ICPC2020.

# Introduction:

##   Managing software asset ownership in any organization is important.In this paper, when we refer to 'asset' we include entities as diverse as source-code files, tables in the data warehouse, and software configurations. When we refer to the 'owner' of an asset, we mean this term in a broad sense: a set of people who take responsibility for the asset. Standard processes, e.g., based on escalation, are typically in place to rule out unowned assets, as they would clearly be a cause for concern. A more nuanced question is the one of 'ownership health', i.e., whether each asset is attributed to the 'most suitable' owner.Who is the most suitable owner of a given asset changes over time, e.g., due to reorganization and individual function changes. Attributing assets to owners and measuring ownership health encompasses a combination of static and dynamic properties of the software assets themselves, the workflows for developing and managing the assets, and the structures of the organization that possesses the assets.

# Methodology:

## 2.1 Vocabulary of Ownership Management The term resource alludes to such an element that is a piece of a framework or is controlled by an organization of intrigue.Accept an extraordinary piece of a framework: its resource for proprietor attribution planning or just attribution, which maps advantages for proprietor competitors, which are in this way alluded to as proprietors.The dark bolts on the left express that the resource for proprietor attribution planning is mostly encoded in the benefits themselves, for example, by explanation inside documents or a metastore for tables, in which case extraction can be applied to resources or conceivably to logs that record the proprietors 'in real life'. 
The quantity of oncall turns is under 10k. Number of proprietor possibility for a given resource a. It is frequently conceivable, subject to heuristics dependent on key highlights, to limit to a short rundown of proprietor applicants that are at all conceivable for the benefit an and that should be positioned in this manner. 
The day by day stir for source-code documents in one of the greater mono repos of Facebook is around 100k. Every day proprietor beat for resource type t. Such stir is important as heuristics/ML should computerize these changes. 
For a significant resource type for planned pipelines in the information distribution center with about 100k resources, the totaled day by day proprietor beat in the course of the most recent 4 months is about 10k while there were a few days with a few several influenced resources - this is a result of organized endeavors on possession the executives at Facebook, in light of Ownesty or something else. 
3.1 Heterogeneity of Owned Assets Ownership suggestion - particularly when concentrating on code resources - is identified with code origin attribution , as applicable, for instance, for identifying malevolent or copied code, subject to stylometry techniques and the all-encompassing presumption of unmistakable composing style to be seen as a unique mark.Program cutting , idea task , and search-based advancement , just as numerous different examination strategies, have all been utilized to explore auxiliary parts of a product advantage for help software engineers' perception of the benefit.Existing reliance investigations should be additionally summed up to apply better to heterogeneous resources and the issue of ascribing advantages for proprietors. 
Provenance or ancestry might be focused on conditions for information resources while data stream might be focused on program resources, yet mixes or speculations of such techniques are expected to cover the advantage types that happen together by and by Workflow and Organizational Aspects Attribution of resources for proprietors likewise needs to consider communications of proprietor competitors with the benefits.
Obviously, possession proposal requires a speculation of the investigation of connections to represent the various sorts of advantages and proprietor competitors and differing types of communication. To be more concrete, hierarchical structure may bolster better comprehension of possession in that, for instance, the wellbeing of a specific attribution of a resource for a proprietor may rely upon past, later, and up and coming changes to groups or individual jobs. 
The accompanying space explicit requirements challenge the arrangement of interpretable and reasonable models for possession suggestion; devoted exploration is required in this way: The attribution connection among resources and proprietor applicants might be naturally uncertain.

# Result:

## This paper describes the overall idea of possession the board and the particular parts of utilizing proprietorship proposal for ascribing advantages for proprietors and estimating the wellbeing of any such attribution for huge and complex activities and frameworks. The suggestion of reasonable proprietors and the evaluation of possession wellbeing depends on information removed from resources, work processes and authoritative structures. 
They have acquainted the Facebook Ownesty framework with delineate the pragmatic modern significance of the going with proprietorship research plan. 
We additionally set out open issues and challenges and their connections to existing examination exercises and networks.


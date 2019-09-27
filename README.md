# Recent Papers Related To Bug Detection

# All Papers (Classification according to Conference)

- **FSE 2019**
  - []

- **NDSS 2019**
  - [Profit: Detecting and Quantifying Side Channels in Networked Applications](#profit-detecting-and-quantifying-side-channels-in-networked-applications-ndss-2019)
  - [CRCount: Pointer Invalidation with Reference Counting to Mitigate Use-after-free in Legacy C/C++](#crcount-pointer-invalidation-with-reference-counting-to-mitigate-use-after-free-in-legacy-cc-ndss-2019)

- **PLDI 2018**
  - [Effectivesan: type and memory error detection using dynamically typed C/C++](#effectivesan-type-and-memory-error-detection-using-dynamically-typed-cc-pldi-2018)

- **NDSS 2017**
  - [Stack Bounds Protection with Low Fat Pointers](#stack-bounds-protection-with-low-fat-pointers-ndss-2017)
    



# All Papers (Classification according to Subject)

- **Concurrency Bugs**
  - [ (FSE 2019)]()

- **Side Channels Attack**
  - [Profit: Detecting and Quantifying Side Channels in Networked Applications (NDSS 2019)](#profit-detecting-and-quantifying-side-channels-in-networked-applications-ndss-2019)

- **Memory Error Detection**
  - [CRCount: Pointer Invalidation with Reference Counting to Mitigate Use-after-free in Legacy C/C++ (NDSS 2019)](#crcount-pointer-invalidation-with-reference-counting-to-mitigate-use-after-free-in-legacy-cc-ndss-2019)
  - [Effectivesan: type and memory error detection using dynamically typed C/C++ (PLDI 2018)](#effectivesan-type-and-memory-error-detection-using-dynamically-typed-cc-pldi-2018)
  - [Stack Bounds Protection with Low Fat Pointers (NDSS 2017)](#stack-bounds-protection-with-low-fat-pointers-ndss-2017)

- **Learning-based Approach**
  - [](#)






# NDSS 2019

### Profit: Detecting and Quantifying Side Channels in Networked Applications (NDSS 2019)

* <img src="image/pdf_24px.png">[Paper](./Paper/NDSS19_Profit.pdf)

* <img src="image/ppt_24px.png">[Slides](https://www.ndss-symposium.org/wp-content/uploads/ndss2019_05B-2_Rosner_slides.pdf)

**Abstract:** We present a black-box, dynamic technique to detect and quantify side-channel information leaks in networked applications that communicate through a TLS-encrypted stream. Given a user-supplied profiling-input suite in which some aspect of the inputs is marked as secret, we run the application over the inputs and capture a collection of variable-length network packet traces. The captured traces give rise to a vast side-channel feature space, including the size and timestamp of each individual packet as well as their aggregations (such as total time, median size, etc.) over every possible subset of packets. Finding the features that leak the most information is a difficult problem.

Our approach addresses this problem in three steps: 1) Global analysis of traces for their alignment and identification of emph{phases} across traces; 2) Feature extraction using the identified phases; 3) Information leakage quantification and ranking of features via estimation of probability distribution.

We embody this approach in a tool called Profit and experimentally evaluate it on a benchmark of applications from the DARPA STAC program, which were developed to assess the effectiveness of side-channel analysis techniques. Our experimental results demonstrate that, given suitable profiling-input suites, Profit is successful in automatically detecting information-leaking features in applications, and correctly ordering the strength of the leakage for differently-leaking variants of the same application.


### CRCount: Pointer Invalidation with Reference Counting to Mitigate Use-after-free in Legacy C/C++ (NDSS 2019)

* <img src="image/pdf_24px.png">[Paper](./Paper/NDSS19_CRCount.pdf)

* <img src="image/ppt_24px.png">[Slides](https://www.ndss-symposium.org/wp-content/uploads/ndss2019_05A-4_Shin_slides.pdf.pdf)

**Abstract:** Pointer invalidation has been a popular approach adopted in many recent studies to mitigate use-after-free errors. The approach can be divided largely into two different schemes: explicit invalidation and implicit invalidation. The former aims to eradicate the root cause of use-after-free errors by invalidating every dangling pointer one by one explicitly. In contrast, the latter aims to prevent dangling pointers by freeing an object only if there is no pointer referring to it. A downside of the explicit scheme is that it is expensive, as it demands high-cost algorithms or a large amount of space to maintain every up-to-date list of pointer locations linking to each object at all times. Implicit invalidation is more efficient in that even without any explicit effort, it can eliminate dangling pointers by leaving objects undeleted until all the links between the objects and their referring pointers vanish by themselves during program execution. However, such an argument only holds if the scheme knows exactly when each link is created and deleted. Reference counting is a traditional method to determine the existence of reference links between objects and pointers. Unfortunately, impeccable reference counting for legacy C/C++ code is very difficult and expensive to achieve in practice, mainly because of the type unsafe operations in the code. In this paper, we present a solution, called CRCount, to the use-after-free problem in legacy C/C++. For effective and efficient problem solving, CRCount is armed with the pointer footprinting technique that enables us to compute, with high accuracy, the reference count of every object referred to by the pointers in the legacy code. Our experiments demonstrate that CRCount mitigates the use-after-free errors with a lower performance-wise and space-wise overhead than the existing pointer invalidation solutions.




# PLDI 2018 

### Effectivesan: type and memory error detection using dynamically typed C/C++ (PLDI 2018)

* <img src="image/pdf_24px.png">[Paper](./Paper/PLDI18_EffectiveSan.pdf)

* <img src="image/github_24px.png">[Code](https://github.com/GJDuck/EffectiveSan)

**Abstract:** Low-level programming languages with weak/static type systems, such as C and C++, are vulnerable to errors relating to the misuse of memory at runtime, such as (sub-)object bounds overflows, (re)use-after-free, and type confusion. Such errors account for many security and other undefined behavior bugs for programs written in these languages. In this paper, we introduce the notion of dynamically typed C/C++, which aims to detect such errors by dynamically checking the "effective" type of each object before use at runtime. We also present an implementation of dynamically typed C/C++ in the form of the Effective Type Sanitizer (EffectiveSan). EffectiveSan enforces type and memory safety using a combination of low-fat pointers, type meta data and type/bounds check instrumentation. We evaluate EffectiveSan against the SPEC2006 benchmark suite and the Firefox web browser, and detect several new type and memory errors. We also show that EffectiveSan achieves high compatibility and reasonable overheads for the given error coverage. Finally, we highlight that EffectiveSan is one of only a few tools that can detect sub-object bounds errors, and uses a novel approach (dynamic type checking) to do so.




# NDSS 2017

### Stack Bounds Protection with Low Fat Pointers (NDSS 2017)

* <img src="image/pdf_24px.png">[Paper](./Paper/NDSS17_LowFat.pdf)

* <img src="image/github_24px.png">[Code](https://github.com/GJDuck/LowFat)

**Abstract:** Object bounds overflow errors are a common source of security vulnerabilities. In principle, bounds check instrumentation eliminates the problem, but is hampered by limited compatibility against un-instrumented code and high overheads. On 64-bit systems, low-fat pointers are a recent scheme for implementing efficient and compatible bounds checking by transparently encoding meta information within the native pointer representation itself. However, low-fat pointers are traditionally used for heap objects only, where the allocator has sufficient control over object location necessary for the encoding. This is a problem for stack allocation, where there exist strong constraints regarding the location of stack objects that is apparently incompatible with low-fat pointers. In this paper, we present an extension of low-fat pointers to stack objects by using a collection of techniques, such as pointer mirroring and memory aliasing, thereby allowing stack objects to enjoy bounds error protection from instrumented code. Our extension is compatible with common special uses of the stack, such as alloca, setjmp and longjmp, exceptions, and multi-threading, which rely on direct manipulation of the stack pointer. Our experiments show that we successfully extend the advantages of the low-fat pointer encoding to stack objects. The end result is competitive bounds checking instrumentation for the stack and heap with low memory and runtime overheads, and high compatibility with un-instrumented legacy code.
---
sectionid: overview
layout: doc_page
---

<h3><i>Data Sketches</i> is a Java software library of <a href="SketchOrigins.html">sketch</a> algorithms and related APIs that provide a comprehensive basis for the analysis of sets of unique identifiers in the context of big data.</h3>

<h2>Key Features</h2>

<h3>Solves Computational Challenges Associated with Unique Identifiers and Duplicates</h3>
  * <b>Estimating cardinality</b> in the context of many duplicates.
  * Performing <a href="ThetaSketchSetOps.html">set operations</a> (e.g., Union, Intersection, and Difference) on sets of unique identifiers
  * Obtaining estimates of the <b>distribution of the error</b> of the result
  * Enables <b>extended analysis</b> of these sets through associations, which could include approximate joins and behavior analysis[1]

<h3>Multiple sketch algorithms</h3>
* Theta Sketches that enable Set Operations
* <a href="HLL.html">HLL</a> sketches for the best accuracy/storage trade-off where only counting and merging are required.
* Tuple Sketches for aggregating associative behaviors[1].

<h3>Designed for Large-scale Computing Systems</h3>
* <b>Small Footprint Per Sketch</b>
  * The operating and storage footprint for both row and column oriented storage are minimized with 
<a href="ThetaSize.html">compact binary representations</a>, which are much smaller than the raw input stream and with a well defined upper bound of size.

* <b>Speed</b>
  * These single-pass, "one-touch" algorithms are <a href="UpdateSpeed.html"><i>fast</i></a> to enable real-time processing capability.
  * Coupled with the compact binary representations, in many cases the need for costly serialization and deserialization has been eliminated.
  * The sketch data structures are "additive" and embarassingly paralelizable and can be merged without losing relative accuracy.

* <b>Adaptors for Grid Computing</b>
  * Adaptors for <a href="Adaptors.html">Hadoop, Druid, Pig, and Hive[1]</a> are also included that implement the major functionality of the core algorithms.

* <b>Easy to Integrate</b>
  * Can be integrated into virtually any Java-base system environment
  * The core library has no dependencies outside of Java.
  * The Hadoop, Druid, Pig, and Hive adaptor classes, are provided in separate repositories.
  * Maven deployable.

* <b>Specific Sketch Features</b>
  * <b>Hash Seed Handling</b>. Additional protection for managing hash seeds which is particularly important when processing sensitive user identifiers.
  * <a href="Sampling.html"><b>Sampling</b></a>. Built-in up-front sampling for cases where additional contol is required to limit overall memory consumption when dealing with millions of sketches.
  * Off-Heap <a href="MemoryPackage.html"><b>Memory Package</b></a>.  Large query systems often require their own heaps outside the JVM in order to better manage garbage collection latencies. The sketches in this package are designed to operate either on-heap or off-heap.
  * Built-in <b>Upper-Bound and Lower-Bound estimators</b>. You are never in the dark about how good of an estimate the sketch is providing.  All the sketches are able to estimate the upper and lower bounds of the estimate given a confidence level.
  * User configurable trade-offs of accuracy vs. storage space as well as other performance tuning options.
  
* <b>Built-In, General Purpose Functions</b>
  * General purpose Memory package for managing data off the Java Heap.  This enables systems designers the ability to manage their own large data heaps with dedicated processor threads that would otherwise put undue pressure on the Java heap and its garbage collection.
  * General purpose implementaion of Austin Appleby's 128-bit MurmurHash3 algorithm, with a number of useful extensions.

<h3>Robust, High Quality Implementations.</h3>
* Extensive test code leveraging <a href="http://testng.org">TestNG</a>.
* Benchmarking, speed and accuracy characterization and performance testing code included in the <i>test</i> package.
* Test Code coverage is > 90% as measured by <a href="https://www.atlassian.com/software/clover/overview">Atlassian Clover</a>.
* Comprehensive Javadocs that satisfy <a href="http://www.oracle.com/technetwork/java/index.html">Java JDK8</a> standards.
* Suitable for production environments.

<h3>Opportunities to Extend</h3>
* There is ample opportunity for interested parties to contribute additional algorithms in this exciting area.
<br>
<br>
<h5>1. Coming soon!</h5>

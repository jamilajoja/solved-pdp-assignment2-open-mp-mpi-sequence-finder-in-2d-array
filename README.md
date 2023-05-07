Download Link: https://assignmentchef.com/product/solved-pdp-assignment2-open-mp-mpi-sequence-finder-in-2d-array
<br>
Please state the assessment criteria applied to this assignment, such as:

<ul>

 <li>Correctness of the work.</li>

 <li>Presentation, including compliance with the specified file format.</li>

 <li>Evidence of critical thinking and analysis.</li>

 <li>Originality, quality and thoroughness of the work.</li>

 <li>Research correct academic approach.</li>

 <li>Proper treatment of sources.</li>

 <li>Demo of code will be in lab, failing to show work in lab receive deduction of 50% of total assignment grade.</li>

</ul>

<em>Academic Dishonesty: All of your assignments need to represent your own effort. Assignments should be done without consultation with other students and you should not share your source code with others. Any assignment submitted that is essentially the same, as someone else’s will not be accepted<strong>. ALL matching assignments will receive 0 credits.</strong> </em>

<strong>                 </strong>

Your task is to search for a number is 2-D matrix of random single digit numbers, the idea of the solution is to parallelize the search between all possible threads and count each occurrence.

Make sure to include timing to your code, you need to submit two solutions using MPI and OpenMP:




<ol>

 <li><strong>OpenMP C file and results of execution.                                     </strong></li>

 <li><strong>Find neighbouring numbers.                                                             </strong></li>

 <li><strong>Repeat part 1 using MPI C file and results of execution. </strong></li>

</ol>

<strong>Example: looking for digit 10 </strong>

<table width="601">

 <tbody>

  <tr>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>2 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>5 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>1 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>5 </strong></td>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>1 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>5 </strong></td>

   <td width="60"><strong>8 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>3 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>8 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>8 </strong></td>

   <td width="60"><strong>5 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>1 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>4 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>5 </strong></td>

   <td width="60"><strong>8 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>3 </strong></td>

   <td width="60"><strong>5 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>8 </strong></td>

   <td width="60"><strong>5 </strong></td>

   <td width="60"><strong>9 </strong></td>

   <td width="60"><strong>8 </strong></td>

   <td width="60"><strong>1 </strong></td>

   <td width="60"><strong>6 </strong></td>

  </tr>

  <tr>

   <td width="60"><strong>8 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>4 </strong></td>

   <td width="60"><strong>8 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>2 </strong></td>

   <td width="60"><strong>6 </strong></td>

   <td width="60"><strong>0 </strong></td>

   <td width="60"><strong>7 </strong></td>

   <td width="60"><strong>2 </strong></td>

  </tr>

 </tbody>

</table>



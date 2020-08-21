Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`FANN_TRAIN_INCREMENTAL`** (<span class="type">integer</span>)  
<span class="simpara"> Standard backpropagation algorithm, where the
weights are updated after each training pattern. This means that the
weights are updated many times during a single epoch. For this reason
some problems, will train very fast with this algorithm, while other
more advanced problems will not train very well. </span>

**`FANN_TRAIN_BATCH`** (<span class="type">integer</span>)  
<span class="simpara"> Standard backpropagation algorithm, where the
weights are updated after calculating the mean square error for the
whole training set. This means that the weights are only updated once
during a epoch. For this reason some problems, will train slower with
this algorithm. But since the mean square error is calculated more
correctly than in incremental training, some problems will reach a
better solutions with this algorithm. </span>

**`FANN_TRAIN_RPROP`** (<span class="type">integer</span>)  
<span class="simpara"> A more advanced batch training algorithm which
achieves good results for many problems. The RPROP training algorithm is
adaptive, and does therefore not use the learning\_rate. Some other
parameters can however be set to change the way the RPROP algorithm
works, but it is only recommended for users with insight in how the
RPROP training algorithm works. The RPROP training algorithm is
described by \[Riedmiller and Braun, 1993\], but the actual learning
algorithm used here is the iRPROP- training algorithm which is described
by \[Igel and Husken, 2000\] which is an variety of the standard RPROP
training algorithm. </span>

**`FANN_TRAIN_QUICKPROP`** (<span class="type">integer</span>)  
<span class="simpara"> A more advanced batch training algorithm which
achieves good results for many problems. The quickprop training
algorithm uses the learning\_rate parameter along with other more
advanced parameters, but it is only recommended to change these advanced
parameters, for users with insight in how the quickprop training
algorithm works. The quickprop training algorithm is described by
\[Fahlman, 1988\]. </span>

**`FANN_TRAIN_SARPROP`** (<span class="type">integer</span>)  
<span class="simpara"> Even more advance training algorithm. Only for
version 2.2 </span>

<!-- -->

**`FANN_LINEAR`** (<span class="type">integer</span>)  
<span class="simpara"> Linear activation function. </span>

**`FANN_THRESHOLD`** (<span class="type">integer</span>)  
<span class="simpara"> Threshold activation function. </span>

**`FANN_THRESHOLD_SYMMETRIC`** (<span class="type">integer</span>)  
<span class="simpara"> Threshold activation function. </span>

**`FANN_SIGMOID`** (<span class="type">integer</span>)  
<span class="simpara"> Sigmoid activation function. </span>

**`FANN_SIGMOID_STEPWISE`** (<span class="type">integer</span>)  
<span class="simpara"> Stepwise linear approximation to sigmoid. </span>

**`FANN_SIGMOID_SYMMETRIC`** (<span class="type">integer</span>)  
<span class="simpara"> Symmetric sigmoid activation function, aka. tanh.
</span>

**`FANN_SIGMOID_SYMMETRIC_STEPWISE`** (<span class="type">integer</span>)  
<span class="simpara"> Stepwise linear approximation to symmetric
sigmoid </span>

**`FANN_GAUSSIAN`** (<span class="type">integer</span>)  
<span class="simpara"> Gaussian activation function. </span>

**`FANN_GAUSSIAN_SYMMETRIC`** (<span class="type">integer</span>)  
<span class="simpara"> Symmetric gaussian activation function. </span>

**`FANN_GAUSSIAN_STEPWISE`** (<span class="type">integer</span>)  
<span class="simpara"> Stepwise gaussian activation function. </span>

**`FANN_ELLIOT`** (<span class="type">integer</span>)  
<span class="simpara"> Fast (sigmoid like) activation function defined
by David Elliott. </span>

**`FANN_ELLIOT_SYMMETRIC`** (<span class="type">integer</span>)  
<span class="simpara"> Fast (symmetric sigmoid like) activation function
defined by David Elliott. </span>

**`FANN_LINEAR_PIECE`** (<span class="type">integer</span>)  
<span class="simpara"> Bounded linear activation function. </span>

**`FANN_LINEAR_PIECE_SYMMETRIC`** (<span class="type">integer</span>)  
<span class="simpara"> Bounded linear activation function. </span>

**`FANN_SIN_SYMMETRIC`** (<span class="type">integer</span>)  
<span class="simpara"> Periodical sinus activation function. </span>

**`FANN_COS_SYMMETRIC`** (<span class="type">integer</span>)  
<span class="simpara"> Periodical cosinus activation function. </span>

**`FANN_SIN`** (<span class="type">integer</span>)  
<span class="simpara"> Periodical sinus activation function. </span>

**`FANN_COS`** (<span class="type">integer</span>)  
<span class="simpara"> Periodical cosinus activation function. </span>

<!-- -->

**`FANN_ERRORFUNC_LINEAR`** (<span class="type">integer</span>)  
<span class="simpara"> Standard linear error function. </span>

**`FANN_ERRORFUNC_TANH`** (<span class="type">integer</span>)  
<span class="simpara"> Tanh error function; usually better but may
require a lower learning rate. This error function aggressively targets
outputs that differ much from the desired, while not targeting outputs
that only differ slightly. Not recommended for cascade or incremental
training. </span>

<!-- -->

**`FANN_STOPFUNC_MSE`** (<span class="type">integer</span>)  
<span class="simpara"> Stop criteria is Mean Square Error (MSE) value.
</span>

**`FANN_STOPFUNC_BIT`** (<span class="type">integer</span>)  
<span class="simpara"> Stop criteria is number of bits that fail. The
number of bits means the number of output neurons which differs more
than the bit fail limit (see fann\_get\_bit\_fail\_limit,
fann\_set\_bit\_fail\_limit). The bits are counted in all of the
training data, so this number can be higher than the number of training
data. </span>

<!-- -->

**`FANN_NETTYPE_LAYER`** (<span class="type">integer</span>)  
<span class="simpara"> Each layer only has connections to the next
layer. </span>

**`FANN_NETTYPE_SHORTCUT`** (<span class="type">integer</span>)  
<span class="simpara"> Each layer has connections to all following
layers </span>

<!-- -->

**`FANN_E_NO_ERROR`** (<span class="type">integer</span>)  
<span class="simpara"> No error. </span>

**`FANN_E_CANT_OPEN_CONFIG_R`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to open configuration file for reading.
</span>

**`FANN_E_CANT_OPEN_CONFIG_W`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to open configuration file for writing.
</span>

**`FANN_E_WRONG_CONFIG_VERSION`** (<span class="type">integer</span>)  
<span class="simpara"> Wrong version of configuration file. </span>

**`FANN_E_CANT_READ_CONFIG`** (<span class="type">integer</span>)  
<span class="simpara"> Error reading info from configuration file.
</span>

**`FANN_E_CANT_READ_NEURON`** (<span class="type">integer</span>)  
<span class="simpara"> Error reading neuron info from configuration
file. </span>

**`FANN_E_CANT_READ_CONNECTIONS`** (<span class="type">integer</span>)  
<span class="simpara"> Error reading connections from configuration
file. </span>

**`FANN_E_WRONG_NUM_CONNECTIONS`** (<span class="type">integer</span>)  
<span class="simpara"> Number of connections not equal to the number
expected. </span>

**`FANN_E_CANT_OPEN_TD_W`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to open train data file for writing.
</span>

**`FANN_E_CANT_OPEN_TD_R`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to open train data file for reading.
</span>

**`FANN_E_CANT_READ_TD`** (<span class="type">integer</span>)  
<span class="simpara"> Error reading training data from file. </span>

**`FANN_E_CANT_ALLOCATE_MEM`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to allocate memory. </span>

**`FANN_E_CANT_TRAIN_ACTIVATION`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to train with the selected activation
function. </span>

**`FANN_E_CANT_USE_ACTIVATION`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to use the selected activation function.
</span>

**`FANN_E_TRAIN_DATA_MISMATCH`** (<span class="type">integer</span>)  
<span class="simpara"> Irreconcilable differences between two struct
fann\_train\_data structures. </span>

**`FANN_E_CANT_USE_TRAIN_ALG`** (<span class="type">integer</span>)  
<span class="simpara"> Unable to use the selected training algorithm.
</span>

**`FANN_E_TRAIN_DATA_SUBSET`** (<span class="type">integer</span>)  
<span class="simpara"> Trying to take subset which is not within the
training set. </span>

**`FANN_E_INDEX_OUT_OF_BOUND`** (<span class="type">integer</span>)  
<span class="simpara"> Index is out of bound. </span>

**`FANN_E_SCALE_NOT_PRESENT`** (<span class="type">integer</span>)  
<span class="simpara"> Scaling parameters not present. </span>

**`FANN_E_INPUT_NO_MATCH`** (<span class="type">integer</span>)  
<span class="simpara"> The number of input neurons in the ann data do
not match </span>

**`FANN_E_OUTPUT_NO_MATCH`** (<span class="type">integer</span>)  
<span class="simpara"> The number of output neurons in the ann and data
do not match. </span>

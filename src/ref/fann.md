fann\_cascadetrain\_on\_data
============================

Trains on an entire dataset, for a period of time using the Cascade2
training algorithm

### Description

<span class="type">bool</span> <span
class="methodname">fann\_cascadetrain\_on\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$max_neurons`</span> , <span class="methodparam"><span
class="type">int</span> `$neurons_between_reports`</span> , <span
class="methodparam"><span class="type">float</span>
`$desired_error`</span> )

The cascade output change fraction is a number between 0 and 1
determining how large a fraction the <span
class="function">fann\_get\_MSE</span> value should change within <span
class="function">fann\_get\_cascade\_output\_stagnation\_epochs</span>
during training of the output connections, in order for the training not
to stagnate. If the training stagnates, the training of the output
connections will be ended and new candidates will be prepared.

This training uses the parameters set using the fann\_set\_cascade\_...,
but it also uses another training algorithm as it’s internal training
algorithm. This algorithm can be set to either **`FANN_TRAIN_RPROP`** or
**`FANN_TRAIN_QUICKPROP`** by <span
class="function">fann\_set\_training\_algorithm</span>, and the
parameters set for these training algorithms will also affect the
cascade training.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`data`  
Neural network training data <span class="type">resource</span>.

`max_neurons`  
The maximum number of neurons to be added to neural network.

`neurons_between_reports`  
The number of neurons between printing a status report. A value of zero
means no reports should be printed.

`desired_error`  
The desired <span class="function">fann\_get\_MSE</span> or <span
class="function">fann\_get\_bit\_fail</span>, depending on which stop
function is chosen by <span
class="function">fann\_set\_train\_stop\_function</span>

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_cascadetrain\_on\_file</span>

fann\_cascadetrain\_on\_file
============================

Trains on an entire dataset read from file, for a period of time using
the Cascade2 training algorithm

### Description

<span class="type">bool</span> <span
class="methodname">fann\_cascadetrain\_on\_file</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">int</span> `$max_neurons`</span> , <span
class="methodparam"><span class="type">int</span>
`$neurons_between_reports`</span> , <span class="methodparam"><span
class="type">float</span> `$desired_error`</span> )

Does the same as <span
class="function">fann\_cascadetrain\_on\_data</span>, but reads the
training data directly from a file.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`filename`  
A file containing the data for training.

`max_neurons`  
The maximum number of neurons to be added to neural network

`neurons_between_reports`  
The number of neurons between printing a status report. A value of zero
means no reports should be printed.

`desired_error`  
The desired <span class="function">fann\_get\_MSE</span> or <span
class="function">fann\_get\_bit\_fail</span>, depending on which stop
function is chosen by <span
class="function">fann\_set\_train\_stop\_function</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_cascadetrain\_on\_data</span>

fann\_clear\_scaling\_params
============================

Clears scaling parameters

### Description

<span class="type">bool</span> <span
class="methodname">fann\_clear\_scaling\_params</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Clears scaling parameters.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

fann\_copy
==========

Creates a copy of a fann structure

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_copy</span> ( <span class="methodparam"><span
class="type">resource</span> `$ann`</span> )

Creates a copy of a fann structure.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Returns a copy of neural network resource on success, or **`FALSE`** on
error

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_test</span>

fann\_create\_from\_file
========================

Constructs a backpropagation neural network from a configuration file

### Description

<span class="type">resource</span> <span
class="methodname">fann\_create\_from\_file</span> ( <span
class="methodparam"><span class="type">string</span>
`$configuration_file`</span> )

Constructs a backpropagation neural network from a configuration file,
which have been saved by <span class="function">fann\_save</span>.

### Parameters

`configuration_file`  
The configuration file path.

### Return Values

Returns a neural network <span class="type">resource</span> on success,
or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_save</span>

fann\_create\_shortcut\_array
=============================

Creates a standard backpropagation neural network which is not fully
connectected and has shortcut connections

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_create\_shortcut\_array</span> ( <span
class="methodparam"><span class="type">int</span> `$num_layers`</span> ,
<span class="methodparam"><span class="type">array</span>
`$layers`</span> )

Creates a standard backpropagation neural network which is not fully
connectected and has shortcut connections using an array of layers
sizes.

### Parameters

`num_layers`  
The total number of layers including the input and the output layer.

`layers`  
An array of layers sizes.

### Return Values

Returns a neural network resource on success, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_create\_shortcut</span>
-   <span class="function">fann\_create\_sparse</span>
-   <span class="function">fann\_create\_standard</span>

fann\_create\_shortcut
======================

Creates a standard backpropagation neural network which is not fully
connectected and has shortcut connections

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_create\_shortcut</span> ( <span
class="methodparam"><span class="type">int</span> `$num_layers`</span> ,
<span class="methodparam"><span class="type">int</span>
`$num_neurons1`</span> , <span class="methodparam"><span
class="type">int</span> `$num_neurons2`</span> , <span
class="methodparam"><span class="type">int</span> `$num_neuronsN`</span>
)

Creates a standard backpropagation neural network, which is not fully
connected and which also has shortcut connections.

Shortcut connections are connections that skip layers. A fully connected
network with shortcut connections, is a network where all neurons are
connected to all neurons in later layers. Including direct connections
from the input layer to the output layer.

### Parameters

`num_layers`  
The total number of layers including the input and the output layer.

`num_neurons1`  
Number of neurons in the first layer.

`num_neurons2`  
Number of neurons in the second layer.

`num_neuronsN`  
Number of neurons in other layers.

### Return Values

Returns a neural network resource on success, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_create\_shortcut\_array</span>
-   <span class="function">fann\_create\_sparse</span>
-   <span class="function">fann\_create\_standard</span>

fann\_create\_sparse\_array
===========================

Creates a standard backpropagation neural network, which is not fully
connected using an array of layer sizes

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_create\_sparse\_array</span> ( <span
class="methodparam"><span class="type">float</span>
`$connection_rate`</span> , <span class="methodparam"><span
class="type">int</span> `$num_layers`</span> , <span
class="methodparam"><span class="type">array</span> `$layers`</span> )

Creates a standard backpropagation neural network, which is not fully
connected using an array of layer sizes.

### Parameters

`connection_rate`  
The connection rate controls how many connections there will be in the
network. If the connection rate is set to 1, the network will be fully
connected, but if it is set to 0.5 only half of the connections will be
set. A connection rate of 1 will yield the same result as <span
class="function">fann\_create\_standard</span>.

`num_layers`  
The total number of layers including the input and the output layer.

`layers`  
An array of layer sizes.

### Return Values

Returns a neural network resource on success, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_create\_sparse</span>
-   <span class="function">fann\_create\_standard</span>
-   <span class="function">fann\_create\_shortcut</span>

fann\_create\_sparse
====================

Creates a standard backpropagation neural network, which is not fully
connected

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_create\_sparse</span> ( <span
class="methodparam"><span class="type">float</span>
`$connection_rate`</span> , <span class="methodparam"><span
class="type">int</span> `$num_layers`</span> , <span
class="methodparam"><span class="type">int</span> `$num_neurons1`</span>
, <span class="methodparam"><span class="type">int</span>
`$num_neurons2`</span> , <span class="methodparam"><span
class="type">int</span> `$num_neuronsN`</span> )

Creates a standard backpropagation neural network, which is not fully
connected.

### Parameters

`connection_rate`  
The connection rate controls how many connections there will be in the
network. If the connection rate is set to 1, the network will be fully
connected, but if it is set to 0.5 only half of the connections will be
set. A connection rate of 1 will yield the same result as <span
class="function">fann\_create\_standard</span>.

`num_layers`  
The total number of layers including the input and the output layer.

`num_neurons1`  
Number of neurons in the first layer.

`num_neurons2`  
Number of neurons in the second layer.

`num_neuronsN`  
Number of neurons in other layers.

### Return Values

Returns a neural network resource on success, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_create\_sparse\_array</span>
-   <span class="function">fann\_create\_standard</span>
-   <span class="function">fann\_create\_shortcut</span>

fann\_create\_standard\_array
=============================

Creates a standard fully connected backpropagation neural network using
an array of layer sizes

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_create\_standard\_array</span> ( <span
class="methodparam"><span class="type">int</span> `$num_layers`</span> ,
<span class="methodparam"><span class="type">array</span>
`$layers`</span> )

Creates a standard fully connected backpropagation neural network.

There will be a bias neuron in each layer (except the output layer), and
this bias neuron will be connected to all neurons in the next layer.
When running the network, the bias nodes always emits 1.

To destroy a neural network use the <span
class="function">fann\_destroy</span> function.

### Parameters

`num_layers`  
The total number of layers including the input and the output layer.

`layers`  
An array of layer sizes.

### Return Values

Returns a neural network resource on success, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_create\_standard</span>
-   <span class="function">fann\_create\_sparse</span>
-   <span class="function">fann\_create\_shortcut</span>

fann\_create\_standard
======================

Creates a standard fully connected backpropagation neural network

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_create\_standard</span> ( <span
class="methodparam"><span class="type">int</span> `$num_layers`</span> ,
<span class="methodparam"><span class="type">int</span>
`$num_neurons1`</span> , <span class="methodparam"><span
class="type">int</span> `$num_neurons2`</span> , <span
class="methodparam"><span class="type">int</span> `$num_neuronsN`</span>
)

Creates a standard fully connected backpropagation neural network.

There will be a bias neuron in each layer (except the output layer), and
this bias neuron will be connected to all neurons in the next layer.
When running the network, the bias nodes always emits 1.

To destroy a neural network use the <span
class="function">fann\_destroy</span> function.

### Parameters

`num_layers`  
The total number of layers including the input and the output layer.

`num_neurons1`  
Number of neurons in the first layer.

`num_neurons2`  
Number of neurons in the second layer.

`num_neuronsN`  
Number of neurons in other layers.

### Return Values

Returns a neural network resource on success, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_create\_standard\_array</span>
-   <span class="function">fann\_create\_sparse</span>
-   <span class="function">fann\_create\_shortcut</span>

fann\_create\_train\_from\_callback
===================================

Creates the training data struct from a user supplied function

### Description

<span class="type">resource</span> <span
class="methodname">fann\_create\_train\_from\_callback</span> ( <span
class="methodparam"><span class="type">int</span> `$num_data`</span> ,
<span class="methodparam"><span class="type">int</span>
`$num_input`</span> , <span class="methodparam"><span
class="type">int</span> `$num_output`</span> , <span
class="methodparam"><span class="type">callable</span>
`$user_function`</span> )

Creates the training data struct from a user supplied function. As the
training data are numerable (data 1, data 2...), the user must write a
function that receives the number of the training data set (input,
output) and returns the set.

### Parameters

`num_data`  
The number of training data

`num_input`  
The number of inputs per training data

`num_output`  
The number of ouputs per training data

`user_function`  
The user supplied function with following parameters:

-   *num* - The number of the training data set
-   *num\_input* - The number of inputs per training data
-   *num\_output* - The number of ouputs per training data

The function should return an associative array with keys *input* and
*output* and two array values of input and output.

### Return Values

Returns a train data <span class="type">resource</span> on success, or
**`FALSE`** on error.

### Examples

**Example \#1 <span
class="methodname">fann\_create\_train\_from\_callback</span> example**

``` php
<?php
function create_train_callback($num_data, $num_input, $num_output) {
    return array(
        "input" => array_fill(0, $num_input, 1),
        "output" => array_fill(0, $num_output, 1),
    );
}

$num_data = 3;
$num_input = 2;
$num_output = 1;
$train_data = fann_create_train_from_callback($num_data, $num_input, $num_output, "create_train_callback");
if ($train_data) {
    // Do something with $train_data
}
?>
```

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_read\_train\_from\_file</span>
-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_destroy\_train</span>
-   <span class="function">fann\_save\_train</span>

fann\_create\_train
===================

Creates an empty training data struct

### Description

<span class="type">resource</span> <span
class="methodname">fann\_create\_train</span> ( <span
class="methodparam"><span class="type">int</span> `$num_data`</span> ,
<span class="methodparam"><span class="type">int</span>
`$num_input`</span> , <span class="methodparam"><span
class="type">int</span> `$num_output`</span> )

Creates an empty training data struct.

### Parameters

`num_data`  
The number of training data

`num_input`  
The number of inputs per training data

`num_output`  
The number of ouputs per training data

### Return Values

Returns a train data <span class="type">resource</span> on success, or
**`FALSE`** on error.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_read\_train\_from\_file</span>
-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_destroy\_train</span>
-   <span class="function">fann\_save\_train</span>

fann\_descale\_input
====================

Scale data in input vector after get it from ann based on previously
calculated parameters

### Description

<span class="type">bool</span> <span
class="methodname">fann\_descale\_input</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">array</span>
`$input_vector`</span> )

Scale data in input vector after get it from ann based on previously
calculated parameters.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`input_vector`  
Input vector that will be descaled

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_scale\_input</span>
-   <span class="function">fann\_descale\_output</span>

fann\_descale\_output
=====================

Scale data in output vector after get it from ann based on previously
calculated parameters

### Description

<span class="type">bool</span> <span
class="methodname">fann\_descale\_output</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">array</span>
`$output_vector`</span> )

Scale data in output vector after get it from ann based on previously
calculated parameters.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`output_vector`  
Output vector that will be descaled

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_scale\_output</span>
-   <span class="function">fann\_descale\_input</span>

fann\_descale\_train
====================

Descale input and output data based on previously calculated parameters

### Description

<span class="type">bool</span> <span
class="methodname">fann\_descale\_train</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$train_data`</span> )

Descale input and output data based on previously calculated parameters.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`train_data`  
Neural network training data <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_scale\_train</span>
-   <span class="function">fann\_set\_scaling\_params</span>

fann\_destroy\_train
====================

Destructs the training data

### Description

<span class="type">bool</span> <span
class="methodname">fann\_destroy\_train</span> ( <span
class="methodparam"><span class="type">resource</span>
`$train_data`</span> )

Destructs the training data

### Parameters

`train_data`  
Neural network training data <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

fann\_destroy
=============

Destroys the entire network and properly freeing all the associated
memory

### Description

<span class="type">bool</span> <span
class="methodname">fann\_destroy</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Destroys the entire network and properly freeing all the associated
memory.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

fann\_duplicate\_train\_data
============================

Returns an exact copy of a fann train data

### Description

<span class="type">resource</span> <span
class="methodname">fann\_duplicate\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$data`</span> )

Returns an exact copy of a fann train data <span
class="type">resource</span>.

### Parameters

`data`  
Neural network training data <span class="type">resource</span>.

### Return Values

Returns a train data <span class="type">resource</span> on success, or
**`FALSE`** on error.

fann\_get\_activation\_function
===============================

Returns the activation function

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_activation\_function</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span> `$layer`</span>
, <span class="methodparam"><span class="type">int</span>
`$neuron`</span> )

Get the activation function for neuron number *neuron* in layer number
*layer*, counting the input layer as layer 0.

It is not possible to get activation functions for the neurons in the
input layer.

The return value is one of the
<a href="/fann/constants.html#Activation%20functions" class="link">activation functions</a>
constants.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`layer`  
Layer number.

`neuron`  
Neuron number.

### Return Values

<a href="/fann/constants.html#Training%20algorithms" class="link">Learning functions</a>
constant or -1 if the neuron is not defined in the neural network, or
**`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_activation\_function\_layer</span>
-   <span
    class="function">fann\_set\_activation\_function\_hidden</span>
-   <span
    class="function">fann\_set\_activation\_function\_output</span>
-   <span class="function">fann\_set\_activation\_steepness</span>
-   <span class="function">fann\_set\_activation\_function</span>

fann\_get\_activation\_steepness
================================

Returns the activation steepness for supplied neuron and layer number

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_activation\_steepness</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span> `$layer`</span>
, <span class="methodparam"><span class="type">int</span>
`$neuron`</span> )

Get the activation steepness for neuron number *neuron* in layer number
*layer*, counting the input layer as layer 0.

It is not possible to get activation steepness for the neurons in the
input layer.

The steepness of an activation function says something about how fast
the activation function goes from the minimum to the maximum. A high
value for the activation function will also give a more agressive
training.

When training neural networks where the output values should be at the
extremes (usually 0 and 1, depending on the activation function), a
steep activation function can be used (e.g. 1.0).

The default activation steepness is 0.5.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`layer`  
Layer number

`neuron`  
Neuron number

### Return Values

The activation steepness for the neuron or -1 if the neuron is not
defined in the neural network, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_activation\_function</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_layer</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_hidden</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_output</span>
-   <span class="function">fann\_set\_activation\_steepness</span>

fann\_get\_bias\_array
======================

Get the number of bias in each layer in the network

### Description

<span class="type">array</span> <span
class="methodname">fann\_get\_bias\_array</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the number of bias in each layer in the network.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

An array of numbers of bias in each layer

fann\_get\_bit\_fail\_limit
===========================

Returns the bit fail limit used during training

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_bit\_fail\_limit</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Returns the bit fail limit used during training.

The bit fail limit is used during training where the
<a href="/fann/constants.html#Stop%20criteria%20used%20during%20training" class="link">stop function</a>
is set to **`FANN_STOPFUNC_BIT`**.

The limit is the maximum accepted difference between the desired output
and the actual output during training. Each output that diverges more
than this limit is counted as an error bit. This difference is divided
by two when dealing with symmetric activation functions, so that
symmetric and not symmetric activation functions can use the same limit.

The default bit fail limit is 0.35.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The bit fail limit, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_bit\_fail\_limit</span>

fann\_get\_bit\_fail
====================

The number of fail bits

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_bit\_fail</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The number of fail bits; means the number of output neurons which differ
more than the bit fail limit (see <span
class="function">fann\_get\_bit\_fail\_limit</span>, <span
class="function">fann\_set\_bit\_fail\_limit</span>). The bits are
counted in all of the training data, so this number can be higher than
the number of training data.

This value is reset by <span class="function">fann\_reset\_MSE</span>
and updated by all the same functions which also updates the MSE value
(e.g. <span class="function">fann\_test\_data</span>, <span
class="function">fann\_train\_epoch</span>)

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of bits fail, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_get\_MSE</span>
-   <span class="function">fann\_reset\_MSE</span>
-   <span class="function">fann\_test\_data</span>
-   <span class="function">fann\_train\_epoch</span>
-   <span class="function">fann\_get\_bit\_fail\_limit</span>
-   <span class="function">fann\_set\_bit\_fail\_limit</span>

fann\_get\_cascade\_activation\_functions\_count
================================================

Returns the number of cascade activation functions

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_activation\_functions\_count</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The number of activation functions in the <span
class="function">fann\_get\_cascade\_activation\_functions</span> array.

The default number of activation functions is 6.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of cascade activation functions, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_get\_cascade\_activation\_functions</span>
-   <span
    class="function">fann\_set\_cascade\_activation\_functions</span>

fann\_get\_cascade\_activation\_functions
=========================================

Returns the cascade activation functions

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_activation\_functions</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The cascade activation functions array is an array of the different
activation functions used by the candidates

See <span class="function">fann\_get\_cascade\_num\_candidates</span>
for a description of which candidate neurons will be generated by this
array.

The default activation functions are **`FANN_SIGMOID`**,
**`FANN_SIGMOID_SYMMETRIC`**, **`FANN_GAUSSIAN`**,
**`FANN_GAUSSIAN_SYMMETRIC`**, **`FANN_ELLIOT`**,
**`FANN_ELLIOT_SYMMETRIC`**.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The cascade activation functions, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_get\_cascade\_activation\_functions\_count</span>
-   <span
    class="function">fann\_set\_cascade\_activation\_functions</span>

fann\_get\_cascade\_activation\_steepnesses\_count
==================================================

The number of activation steepnesses

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_activation\_steepnesses\_count</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The number of activation steepnesses in the <span
class="function">fann\_get\_cascade\_activation\_functions</span> array.

The default number of activation steepnesses is 4.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of activation steepnesses, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_get\_cascade\_activation\_steepnesses</span>
-   <span
    class="function">fann\_set\_cascade\_activation\_functions</span>

fann\_get\_cascade\_activation\_steepnesses
===========================================

Returns the cascade activation steepnesses

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_activation\_steepnesses</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The cascade activation steepnesses array is an array of the different
activation functions used by the candidates.

See <span class="function">fann\_get\_cascade\_num\_candidates</span>
for a description of which candidate neurons will be generated by this
array.

The default activation steepnesses are {0.25, 0.50, 0.75, 1.00}.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The cascade activation steepnesses, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_get\_cascade\_activation\_steepnesses\_count</span>
-   <span
    class="function">fann\_set\_cascade\_activation\_steepnesses</span>

fann\_get\_cascade\_candidate\_change\_fraction
===============================================

Returns the cascade candidate change fraction

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_candidate\_change\_fraction</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The cascade candidate change fraction is a number between 0 and 1
determining how large a fraction the <span
class="function">fann\_get\_MSE</span> value should change within <span
class="function">fann\_get\_cascade\_candidate\_stagnation\_epochs</span>
during training of the candidate neurons, in order for the training not
to stagnate. If the training stagnates, the training of the candidate
neurons will be ended and the best candidate will be selected.

It means that if the MSE does not change by a fraction of <span
class="function">fann\_get\_cascade\_candidate\_change\_fraction</span>
during a period of <span
class="function">fann\_get\_cascade\_candidate\_stagnation\_epochs</span>,
the training of the candidate neurons is stopped because the training
has stagnated.

If the cascade candidate change fraction is low, the candidate neurons
will be trained more and if the fraction is high they will be trained
less.

The default cascade candidate change fraction is 0.01, which is equalent
to a 1% change in MSE.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The cascade candidate change fraction, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_set\_cascade\_candidate\_change\_fraction</span>
-   <span class="function">fann\_get\_MSE</span>
-   <span
    class="function">fann\_get\_cascade\_candidate\_stagnation\_epochs</span>

fann\_get\_cascade\_candidate\_limit
====================================

Return the candidate limit

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_candidate\_limit</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The candidate limit is a limit for how much the candidate neuron may be
trained. The limit is a limit on the proportion between the MSE and
candidate score.

Set this to a lower value to avoid overfitting and to a higher if
overfitting is not a problem.

The default candidate limit is 1000.0.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The candidate limit, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_cascade\_candidate\_limit</span>

fann\_get\_cascade\_candidate\_stagnation\_epochs
=================================================

Returns the number of cascade candidate stagnation epochs

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_candidate\_stagnation\_epochs</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The number of cascade candidate stagnation epochs determines the number
of epochs training is allowed to continue without changing the MSE by a
fraction of <span
class="function">fann\_get\_cascade\_candidate\_change\_fraction</span>.

See more info about this parameter in <span
class="function">fann\_get\_cascade\_candidate\_change\_fraction</span>.

The default number of cascade candidate stagnation epochs is 12.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of cascade candidate stagnation epochs, or **`FALSE`** on
error.

### See Also

-   <span
    class="function">fann\_set\_cascade\_candidate\_stagnation\_epochs</span>
-   <span
    class="function">fann\_get\_cascade\_candidate\_change\_fraction</span>

fann\_get\_cascade\_max\_cand\_epochs
=====================================

Returns the maximum candidate epochs

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_max\_cand\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The maximum candidate epochs determines the maximum number of epochs the
input connections to the candidates may be trained before adding a new
candidate neuron.

The default max candidate epochs is 150.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The maximum candidate epochs, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_cascade\_max\_cand\_epochs</span>

fann\_get\_cascade\_max\_out\_epochs
====================================

Returns the maximum out epochs

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_max\_out\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The maximum out epochs determines the maximum number of epochs the
output connections may be trained after adding a new candidate neuron.

The default max out epochs is 150.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The maximum out epochs, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_cascade\_max\_out\_epochs</span>

fann\_get\_cascade\_min\_cand\_epochs
=====================================

Returns the minimum candidate epochs

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_min\_cand\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The minimum candidate epochs determines the minimum number of epochs the
input connections to the candidates may be trained before adding a new
candidate neuron.

The default min candidate epochs is 50.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The minimum candidate epochs, or **`FALSE`** on error.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_set\_cascade\_min\_cand\_epochs</span>

fann\_get\_cascade\_min\_out\_epochs
====================================

Returns the minimum out epochs

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_min\_out\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The minimum out epochs determines the minimum number of epochs the
output connections must be trained after adding a new candidate neuron.

The default min out epochs is 50.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The minimum out epochs, or **`FALSE`** on error.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_set\_cascade\_min\_out\_epochs</span>

fann\_get\_cascade\_num\_candidate\_groups
==========================================

Returns the number of candidate groups

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_num\_candidate\_groups</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The number of candidate groups is the number of groups of identical
candidates which will be used during training.

This number can be used to have more candidates without having to define
new parameters for the candidates.

See <span class="function">fann\_get\_cascade\_num\_candidates</span>
for a description of which candidate neurons will be generated by this
parameter.

The default number of candidate groups is 2.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of candidate groups, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_set\_cascade\_num\_candidate\_groups</span>

fann\_get\_cascade\_num\_candidates
===================================

Returns the number of candidates used during training

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_num\_candidates</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The number of candidates used during training (calculated by multiplying
<span
class="function">fann\_get\_cascade\_activation\_functions\_count</span>,
<span
class="function">fann\_get\_cascade\_activation\_steepnesses\_count</span>
and <span
class="function">fann\_get\_cascade\_num\_candidate\_groups</span>).

The actual candidates is defined by the <span
class="function">fann\_get\_cascade\_activation\_functions</span> and
<span
class="function">fann\_get\_cascade\_activation\_steepnesses</span>
arrays. These arrays define the activation functions and activation
steepnesses used for the candidate neurons. If there are 2 activation
functions in the activation function array and 3 steepnesses in the
steepness array, then there will be 2x3=6 different candidates which
will be trained. These 6 different candidates can be copied into several
candidate groups, where the only difference between these groups is the
initial weights. If the number of groups is set to 2, then the number of
candidate neurons will be 2x3x2=12. The number of candidate groups is
defined by <span
class="function">fann\_set\_cascade\_num\_candidate\_groups</span>.

The default number of candidates is 6x4x2 = 48

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of candidates used during training, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_get\_cascade\_activation\_functions</span>
-   <span
    class="function">fann\_get\_cascade\_activation\_functions\_count</span>
-   <span
    class="function">fann\_get\_cascade\_activation\_steepnesses</span>
-   <span
    class="function">fann\_get\_cascade\_activation\_steepnesses\_count</span>
-   <span
    class="function">fann\_get\_cascade\_num\_candidate\_groups</span>

fann\_get\_cascade\_output\_change\_fraction
============================================

Returns the cascade output change fraction

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_output\_change\_fraction</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The cascade output change fraction is a number between 0 and 1
determining how large a fraction of the <span
class="function">fann\_get\_MSE</span> value should change within <span
class="function">fann\_get\_cascade\_output\_stagnation\_epochs</span>
during training of the output connections, in order for the training not
to stagnate. If the training stagnates, the training of the output
connections will be ended and new candidates will be prepared.

It means that if the MSE does not change by a fraction of <span
class="function">fann\_get\_cascade\_output\_change\_fraction</span>
during a period of <span
class="function">fann\_get\_cascade\_output\_stagnation\_epochs</span>,
the training of the output connections is stopped because the training
has stagnated.

If the cascade output change fraction is low, the output connections
will be trained more and if the fraction is high, they will be trained
less.

The default cascade output change fraction is 0.01, which is equalent to
a 1% change in MSE.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The cascade output change fraction, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_set\_cascade\_output\_change\_fraction</span>
-   <span class="function">fann\_get\_MSE</span>
-   <span
    class="function">fann\_get\_cascade\_output\_stagnation\_epochs</span>

fann\_get\_cascade\_output\_stagnation\_epochs
==============================================

Returns the number of cascade output stagnation epochs

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_output\_stagnation\_epochs</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The number of cascade output stagnation epochs determines the number of
epochs training is allowed to continue without changing the MSE by a
fraction of <span
class="function">fann\_get\_cascade\_output\_change\_fraction</span>.

See more info about this parameter in <span
class="function">fann\_get\_cascade\_output\_change\_fraction</span>.

The default number of cascade output stagnation epochs is 12.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of cascade output stagnation epochs, or **`FALSE`** on error.

### See Also

-   <span
    class="function">fann\_set\_cascade\_output\_stagnation\_epochs</span>
-   <span
    class="function">fann\_get\_cascade\_output\_change\_fraction</span>

fann\_get\_cascade\_weight\_multiplier
======================================

Returns the weight multiplier

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_cascade\_weight\_multiplier</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The weight multiplier is a parameter which is used to multiply the
weights from the candidate neuron before adding the neuron to the neural
network. This parameter is usually between 0 and 1, and is used to make
the training a bit less aggressive.

The default weight multiplier is 0.4.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The weight multiplier, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_cascade\_weight\_multiplier</span>

fann\_get\_connection\_array
============================

Get connections in the network

### Description

<span class="type">array</span> <span
class="methodname">fann\_get\_connection\_array</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get connections in the network.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

An array of connections in the network

fann\_get\_connection\_rate
===========================

Get the connection rate used when the network was created

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_connection\_rate</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the connection rate used when the network was created.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The connection rate used when the network was created, or **`FALSE`** on
error.

fann\_get\_errno
================

Returns the last error number

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_errno</span> ( <span
class="methodparam"><span class="type">resource</span> `$errdat`</span>
)

Returns the last error number.

### Parameters

`errdat`  
Either neural network <span class="type">resource</span> or neural
network trainining data <span class="type">resource</span>.

### Return Values

The error number, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_reset\_errno</span>
-   <span class="function">fann\_get\_errstr</span>

fann\_get\_errstr
=================

Returns the last errstr

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_errstr</span> ( <span
class="methodparam"><span class="type">resource</span> `$errdat`</span>
)

Returns the last errstr.

### Parameters

`errdat`  
Either neural network <span class="type">resource</span> or neural
network trainining data <span class="type">resource</span>.

### Return Values

The last error string, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_reset\_errstr</span>
-   <span class="function">fann\_get\_errno</span>

fann\_get\_layer\_array
=======================

Get the number of neurons in each layer in the network

### Description

<span class="type">array</span> <span
class="methodname">fann\_get\_layer\_array</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the number of neurons in each layer in the neural network.

Bias is not included so the layers match the fann\_create functions.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

An array of numbers of neurons in each leayer

fann\_get\_learning\_momentum
=============================

Returns the learning momentum

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_learning\_momentum</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The learning momentum can be used to speed up
**`FANN_TRAIN_INCREMENTAL`** training. A too high momentum will however
not benefit training. Setting momentum to 0 will be the same as not
using the momentum parameter. The recommended value of this parameter is
between 0.0 and 1.0.

The default momentum is 0.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

The learning momentum, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_learning\_momentum</span>
-   <span class="function">fann\_set\_training\_algorithm</span>

fann\_get\_learning\_rate
=========================

Returns the learning rate

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_learning\_rate</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The learning rate is used to determine how aggressive training should be
for some of the training algorithms (**`FANN_TRAIN_INCREMENTAL`**,
**`FANN_TRAIN_BATCH`**, **`FANN_TRAIN_QUICKPROP`**). Do however note
that it is not used in **`FANN_TRAIN_RPROP`**.

The default learning rate is 0.7.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The learning rate, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_learning\_rate</span>
-   <span class="function">fann\_set\_training\_algorithm</span>

fann\_get\_MSE
==============

Reads the mean square error from the network

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_MSE</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Reads the mean square error from the network.

Reads the mean square error from the network. This value is calculated
during training or testing and can therefore sometimes be a bit off if
the weights have been changed since the last calculation of the value.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The mean square error, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_test\_data</span>

fann\_get\_network\_type
========================

Get the type of neural network it was created as

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_network\_type</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the type of neural network it was created as.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

<a href="/fann/constants.html#Definition%20of%20network%20types%20used%20by%20fann_get_network_type" class="link">Network type</a>
constant, or **`FALSE`** on error.

fann\_get\_num\_input
=====================

Get the number of input neurons

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_num\_input</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the number of input neurons.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Number of input neurons, or **`FALSE`** on error

fann\_get\_num\_layers
======================

Get the number of layers in the neural network

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_num\_layers</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the number of layers in the neural network.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The number of leayers in the neural network, or **`FALSE`** on error.

fann\_get\_num\_output
======================

Get the number of output neurons

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_num\_output</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the number of output neurons.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Number of output neurons, or **`FALSE`** on error

fann\_get\_quickprop\_decay
===========================

Returns the decay which is a factor that weights should decrease in each
iteration during quickprop training

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_quickprop\_decay</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The decay is a small negative valued number which is a factor that the
weights should decrease in each iteration during quickprop training.
This is used to make sure that the weights do not become too high during
training.

The default decay is -0.0001.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The decay, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_quickprop\_decay</span>

fann\_get\_quickprop\_mu
========================

Returns the mu factor

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_quickprop\_mu</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The mu factor is used to increase and decrease the step-size during
quickprop training. The mu factor should always be above 1, since it
would otherwise decrease the step-size when it was suppose to increase
it.

The default mu factor is 1.75.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The mu factor, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_quickprop\_mu</span>

fann\_get\_rprop\_decrease\_factor
==================================

Returns the increase factor used during RPROP training

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_rprop\_decrease\_factor</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The decrease factor is a value smaller than 1, which is used to decrease
the step-size during RPROP training.

The default decrease factor is 0.5.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The decrease factor, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_rprop\_decrease\_factor</span>

fann\_get\_rprop\_delta\_max
============================

Returns the maximum step-size

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_rprop\_delta\_max</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The maximum step-size is a positive number determining how large the
maximum step-size may be.

The default delta max is 50.0.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The maximum step-size, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_rprop\_delta\_max</span>
-   <span class="function">fann\_get\_rprop\_delta\_min</span>

fann\_get\_rprop\_delta\_min
============================

Returns the minimum step-size

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_rprop\_delta\_min</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The minimum step-size is a small positive number determining how small
the minimum step-size may be.

The default value delta min is 0.0.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The minimum step-size, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_rprop\_delta\_min</span>

fann\_get\_rprop\_delta\_zero
=============================

Returns the initial step-size

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_rprop\_delta\_zero</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The initial step-size is a positive number determining the initial step
size.

The default delta zero is 0.1.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The initial step-size, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_rprop\_delta\_zero</span>
-   <span class="function">fann\_get\_rprop\_delta\_min</span>
-   <span class="function">fann\_get\_rprop\_delta\_max</span>

fann\_get\_rprop\_increase\_factor
==================================

Returns the increase factor used during RPROP training

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_rprop\_increase\_factor</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

The increase factor is a value larger than 1, which is used to increase
the step-size during RPROP training.

The default increase factor is 1.2.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The increase factor, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_rprop\_increase\_factor</span>

fann\_get\_sarprop\_step\_error\_shift
======================================

Returns the sarprop step error shift

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_sarprop\_step\_error\_shift</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Returns the sarprop step error shift.

The default step error shift is 1.385.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The sarprop step error shift , or **`FALSE`** on error.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_set\_sarprop\_step\_error\_shift</span>

fann\_get\_sarprop\_step\_error\_threshold\_factor
==================================================

Returns the sarprop step error threshold factor

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_sarprop\_step\_error\_threshold\_factor</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The sarprop step error threshold factor.

The default factor is 0.1.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The sarprop step error threshold factor, or **`FALSE`** on error.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span
    class="function">fann\_set\_sarprop\_step\_error\_threshold\_factor</span>

fann\_get\_sarprop\_temperature
===============================

Returns the sarprop temperature

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_sarprop\_temperature</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Returns the sarprop temperature.

The default temperature is 0.015.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The sarprop temperature, or **`FALSE`** on error.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_set\_sarprop\_temperature</span>

fann\_get\_sarprop\_weight\_decay\_shift
========================================

Returns the sarprop weight decay shift

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_sarprop\_weight\_decay\_shift</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> )

The sarprop weight decay shift.

The default delta max is -6.644.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The sarprop weight decay shift, or **`FALSE`** on error.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span
    class="function">fann\_set\_sarprop\_weight\_decay\_shift</span>

fann\_get\_total\_connections
=============================

Get the total number of connections in the entire network

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_total\_connections</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the total number of connections in the entire network.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Total number of connections in the entire network, or **`FALSE`** on
error

fann\_get\_total\_neurons
=========================

Get the total number of neurons in the entire network

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_total\_neurons</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Get the total number of neurons in the entire network. This number does
also include the bias neurons, so a 2-4-2 network has 2+4+2 +2(bias) =
10 neurons.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Total number of neurons in the entire network, or **`FALSE`** on error.

fann\_get\_train\_error\_function
=================================

Returns the error function used during training

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_train\_error\_function</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Returns the error function used during training.

The error functions are described further in
<a href="/fann/constants.html#Error%20function%20used%20during%20training" class="link">error functions</a>
constants.

The default error function is **`FANN_ERRORFUNC_TANH`**.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The
<a href="/fann/constants.html#Error%20function%20used%20during%20training" class="link">error function</a>
constant, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_train\_error\_function</span>

fann\_get\_train\_stop\_function
================================

Returns the stop function used during training

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_train\_stop\_function</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Returns the stop function used during training.

The stop functions are described further in
<a href="/fann/constants.html#Stop%20criteria%20used%20during%20training" class="link">stop functions</a>
constants.

The default stop function is **`FANN_STOPFUNC_MSE`**.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

The
<a href="/fann/constants.html#Stop%20criteria%20used%20during%20training" class="link">stop function</a>
constant, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_train\_stop\_function</span>

fann\_get\_training\_algorithm
==============================

Returns the training algorithm

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_get\_training\_algorithm</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> )

Returns the training algorithm. This training algorithm is used by <span
class="function">fann\_train\_on\_data</span> and associated functions.

Note that this algorithm is also used during <span
class="function">fann\_cascadetrain\_on\_data</span>, although only
**`FANN_TRAIN_RPROP`** and **`FANN_TRAIN_QUICKPROP`** is allowed during
cascade training.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

<a href="/fann/constants.html#Training%20algorithms" class="link">Training algorithm</a>
constant, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_set\_training\_algorithm</span>

fann\_init\_weights
===================

Initialize the weights using Widrow + Nguyen’s algorithm

### Description

<span class="type">bool</span> <span
class="methodname">fann\_init\_weights</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$train_data`</span> )

Initialize the weights using Widrow + Nguyen’s algorithm.

This function behaves similarly to <span
class="function">fann\_randomize\_weights</span>. It will use the
algorithm developed by Derrick Nguyen and Bernard Widrow to set the
weights in such a way as to speed up training. This technique is not
always successful, and in some cases can be less efficient than a purely
random initialization.

The algorithm requires access to the range of the input data (for
example largest and smallest input), and therefore accepts a second
argument, data, which is the training data that will be used to train
the network.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`train_data`  
Neural network training data <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_randomize\_weights</span>
-   <span class="function">fann\_read\_train\_from\_file</span>

fann\_length\_train\_data
=========================

Returns the number of training patterns in the train data

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_length\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$data`</span> )

Returns the number of training patterns in the train data <span
class="type">resource</span>.

### Parameters

`data`  
Neural network training data <span class="type">resource</span>.

### Return Values

Number of elements in the train data <span class="type">resource</span>,
or **`FALSE`** on error.

fann\_merge\_train\_data
========================

Merges the train data

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fann\_merge\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$data1`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$data2`</span> )

Merges the data from data1 and data2 into a new train data <span
class="type">resource</span>.

### Parameters

`data1`  
Neural network training data <span class="type">resource</span>.

`data2`  
Neural network training data <span class="type">resource</span>.

### Return Values

New merged train data <span class="type">resource</span>, or **`FALSE`**
on error.

fann\_num\_input\_train\_data
=============================

Returns the number of inputs in each of the training patterns in the
train data

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_num\_input\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$data`</span> )

Returns the number of inputs in each of the training patterns in the
train data <span class="type">resource</span>.

### Parameters

`data`  
Neural network training data <span class="type">resource</span>.

### Return Values

The number of inputs, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_length\_train\_data</span>
-   <span class="function">fann\_num\_output\_train\_data</span>

fann\_num\_output\_train\_data
==============================

Returns the number of outputs in each of the training patterns in the
train data

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">fann\_num\_output\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$data`</span> )

Returns the number of outputs in each of the training patterns in the
train data <span class="type">resource</span>.

### Parameters

`data`  
Neural network training data <span class="type">resource</span>.

### Return Values

The number of outputs, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_length\_train\_data</span>
-   <span class="function">fann\_num\_input\_train\_data</span>

fann\_print\_error
==================

Prints the error string

### Description

<span class="type">void</span> <span
class="methodname">fann\_print\_error</span> ( <span
class="methodparam"><span class="type">resource</span> `$errdat`</span>
)

Prints the error string.

### Parameters

`errdat`  
Either neural network <span class="type">resource</span> or neural
network trainining data <span class="type">resource</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">fann\_get\_errstr</span>

fann\_randomize\_weights
========================

Give each connection a random weight between min\_weight and max\_weight

### Description

<span class="type">bool</span> <span
class="methodname">fann\_randomize\_weights</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$min_weight`</span> , <span class="methodparam"><span
class="type">float</span> `$max_weight`</span> )

Give each connection a random weight between `min_weight` and
`max_weight`

From the beginning the weights are random between -0.1 and 0.1.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`min_weight`  
Minimum weight value

`max_weight`  
Maximum weight value

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_init\_weights</span>

fann\_read\_train\_from\_file
=============================

Reads a file that stores training data

### Description

<span class="type">resource</span> <span
class="methodname">fann\_read\_train\_from\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Reads a file that stores training data.

### Parameters

`filename`  
The input file in the following format:

``` txt
num_train_data num_input num_output
inputdata seperated by space
outputdata seperated by space

.
.
.

inputdata seperated by space
outputdata seperated by space
```

### Return Values

Returns a train data <span class="type">resource</span> on success, or
**`FALSE`** on error.

### Examples

**Example \#1 <span
class="methodname">fann\_read\_train\_from\_file</span> example**

``` php
<?php
$train_data = fann_read_train_from_file("xor.data");
if ($train_data) {
    // Do something with $train_data for XOR function
}
?>
```

Contents of xor.data

``` txt
4 2 1
-1 -1
-1
-1 1
1
1 -1
1
1 1
-1
```

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_destroy\_train</span>
-   <span class="function">fann\_save\_train</span>

fann\_reset\_errno
==================

Resets the last error number

### Description

<span class="type">void</span> <span
class="methodname">fann\_reset\_errno</span> ( <span
class="methodparam"><span class="type">resource</span> `$errdat`</span>
)

Resets the last error number.

### Parameters

`errdat`  
Either neural network <span class="type">resource</span> or neural
network trainining data <span class="type">resource</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">fann\_get\_errno</span>
-   <span class="function">fann\_reset\_errstr</span>

fann\_reset\_errstr
===================

Resets the last error string

### Description

<span class="type">void</span> <span
class="methodname">fann\_reset\_errstr</span> ( <span
class="methodparam"><span class="type">resource</span> `$errdat`</span>
)

Resets the last error string.

### Parameters

`errdat`  
Either neural network <span class="type">resource</span> or neural
network trainining data <span class="type">resource</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">fann\_get\_errstr</span>
-   <span class="function">fann\_reset\_errno</span>

fann\_reset\_MSE
================

Resets the mean square error from the network

### Description

<span class="type">bool</span> <span
class="methodname">fann\_reset\_MSE</span> ( <span
class="methodparam"><span class="type">string</span> `$ann`</span> )

Resets the mean square error from the network.

This function also resets the number of bits that fail.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_MSE</span>
-   <span class="function">fann\_get\_bit\_fail</span>
-   <span class="function">fann\_get\_bit\_fail\_limit</span>

fann\_run
=========

Will run input through the neural network

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">fann\_run</span> ( <span class="methodparam"><span
class="type">resource</span> `$ann`</span> , <span
class="methodparam"><span class="type">array</span> `$input`</span> )

Will run input through the neural network, returning an array of
outputs, the number of which being equal to the number of neurons in the
output layer.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`input`  
Array of input values

### Return Values

Array of output values, or **`FALSE`** on error

fann\_save\_train
=================

Save the training structure to a file

### Description

<span class="type">bool</span> <span
class="methodname">fann\_save\_train</span> ( <span
class="methodparam"><span class="type">resource</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`$file_name`</span> )

Save the training data to a file, with the format as specified in <span
class="function">fann\_read\_train\_from\_file</span>.

### Parameters

`data`  
Neural network training data <span class="type">resource</span>.

`file_name`  
The file name of the file where training data is saved to.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_read\_train\_from\_file</span>

fann\_save
==========

Saves the entire network to a configuration file

### Description

<span class="type">bool</span> <span
class="methodname">fann\_save</span> ( <span class="methodparam"><span
class="type">resource</span> `$ann`</span> , <span
class="methodparam"><span class="type">string</span>
`$configuration_file`</span> )

Saves the entire network to a configuration file.

The configuration file contains all information about the neural network
and enables <span class="function">fann\_create\_from\_file</span> to
create an exact copy of the neural network and all of the parameters
associated with the neural network.

These three parameters (<span
class="function">fann\_set\_callback</span>, <span
class="function">fann\_set\_error\_log</span>, <span
class="function">fann\_set\_user\_data</span>) are NOT saved to the file
because they cannot safely be ported to a different location. Also
temporary parameters generated during training like <span
class="function">fann\_get\_MSE</span> is not saved.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`configuration_file`  
The configuration file path.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_create\_from\_file</span>

fann\_scale\_input\_train\_data
===============================

Scales the inputs in the training data to the specified range

### Description

<span class="type">bool</span> <span
class="methodname">fann\_scale\_input\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span>
`$train_data`</span> , <span class="methodparam"><span
class="type">float</span> `$new_min`</span> , <span
class="methodparam"><span class="type">float</span> `$new_max`</span> )

Scales the inputs in the training data to the specified range.

### Parameters

`train_data`  
Neural network training data <span class="type">resource</span>.

`new_min`  
New minimum after scaling inputs in training data.

`new_max`  
New maximum after scaling inputs in training data.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_scale\_output\_train\_data</span>
-   <span class="function">fann\_scale\_train\_data</span>

fann\_scale\_input
==================

Scale data in input vector before feed it to ann based on previously
calculated parameters

### Description

<span class="type">bool</span> <span
class="methodname">fann\_scale\_input</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">array</span>
`$input_vector`</span> )

Scale data in input vector before feed it to ann based on previously
calculated parameters.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`input_vector`  
Input vector that will be scaled

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_descale\_input</span>
-   <span class="function">fann\_scale\_output</span>

fann\_scale\_output\_train\_data
================================

Scales the outputs in the training data to the specified range

### Description

<span class="type">bool</span> <span
class="methodname">fann\_scale\_output\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span>
`$train_data`</span> , <span class="methodparam"><span
class="type">float</span> `$new_min`</span> , <span
class="methodparam"><span class="type">float</span> `$new_max`</span> )

Scales the outputs in the training data to the specified range.

### Parameters

`train_data`  
Neural network training data <span class="type">resource</span>.

`new_min`  
New minimum after scaling outputs in training data.

`new_max`  
New maximum after scaling outputs in training data.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_scale\_input\_train\_data</span>
-   <span class="function">fann\_scale\_train\_data</span>

fann\_scale\_output
===================

Scale data in output vector before feed it to ann based on previously
calculated parameters

### Description

<span class="type">bool</span> <span
class="methodname">fann\_scale\_output</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">array</span>
`$output_vector`</span> )

Scale data in output vector before feed it to ann based on previously
calculated parameters.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`output_vector`  
Output vector that will be scaled

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_descale\_output</span>
-   <span class="function">fann\_scale\_input</span>

fann\_scale\_train\_data
========================

Scales the inputs and outputs in the training data to the specified
range

### Description

<span class="type">bool</span> <span
class="methodname">fann\_scale\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span>
`$train_data`</span> , <span class="methodparam"><span
class="type">float</span> `$new_min`</span> , <span
class="methodparam"><span class="type">float</span> `$new_max`</span> )

Scales the inputs and outputs in the training data to the specified
range.

### Parameters

`train_data`  
Neural network training data <span class="type">resource</span>.

`new_min`  
New minimum after scaling inputs and outputs in training data.

`new_max`  
New maximum after scaling inputs and outputs in training data.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_scale\_output\_train\_data</span>
-   <span class="function">fann\_scale\_input\_train\_data</span>

fann\_scale\_train
==================

Scale input and output data based on previously calculated parameters

### Description

<span class="type">bool</span> <span
class="methodname">fann\_scale\_train</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$train_data`</span> )

Scale input and output data based on previously calculated parameters.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`train_data`  
Neural network training data <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_descale\_train</span>
-   <span class="function">fann\_set\_scaling\_params</span>

fann\_set\_activation\_function\_hidden
=======================================

Sets the activation function for all of the hidden layers

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_function\_hidden</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span class="type">int</span>
`$activation_function`</span> )

Sets the activation function for all of the hidden layers.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_function`  
The
<a href="/fann/constants.html#Activation%20functions" class="link">activation functions</a>
constant.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_activation\_function</span>
-   <span class="function">fann\_set\_activation\_function\_layer</span>
-   <span
    class="function">fann\_set\_activation\_function\_output</span>
-   <span class="function">fann\_set\_activation\_steepness</span>

fann\_set\_activation\_function\_layer
======================================

Sets the activation function for all the neurons in the supplied layer

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_function\_layer</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$activation_function`</span> , <span class="methodparam"><span
class="type">int</span> `$layer`</span> )

Set the activation function for all the neurons in the layer number
*layer*, counting the input layer as layer 0.

It is not possible to set activation functions for the neurons in the
input layer.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_function`  
The
<a href="/fann/constants.html#Activation%20functions" class="link">activation functions</a>
constant.

`layer`  
Layer number.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_activation\_function</span>
-   <span
    class="function">fann\_set\_activation\_function\_hidden</span>
-   <span
    class="function">fann\_set\_activation\_function\_output</span>
-   <span class="function">fann\_set\_activation\_steepness</span>

fann\_set\_activation\_function\_output
=======================================

Sets the activation function for the output layer

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_function\_output</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span class="type">int</span>
`$activation_function`</span> )

Sets the activation function for the output layer.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_function`  
The
<a href="/fann/constants.html#Activation%20functions" class="link">activation functions</a>
constant.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_activation\_function</span>
-   <span class="function">fann\_set\_activation\_function\_layer</span>
-   <span
    class="function">fann\_set\_activation\_function\_hidden</span>
-   <span class="function">fann\_set\_activation\_steepness</span>

fann\_set\_activation\_function
===============================

Sets the activation function for supplied neuron and layer

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_function</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$activation_function`</span> , <span class="methodparam"><span
class="type">int</span> `$layer`</span> , <span
class="methodparam"><span class="type">int</span> `$neuron`</span> )

Set the activation function for neuron number *neuron* in layer number
*layer*, counting the input layer as layer 0.

It is not possible to set activation functions for the neurons in the
input layer.

When choosing an activation function it is important to note that the
activation functions have different range. **`FANN_SIGMOID`** is e.g. in
the 0 - 1 range while **`FANN_SIGMOID_SYMMETRIC`** is in the -1 - 1
range and **`FANN_LINEAR`** is unbound.

The supplied activation\_function value must be one of the
<a href="/fann/constants.html#Activation%20functions" class="link">activation functions</a>
constants.

The return value is one of the
<a href="/fann/constants.html#Training%20algorithms" class="link">activation functions</a>
constants.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_function`  
The
<a href="/fann/constants.html#Activation%20functions" class="link">activation functions</a>
constant.

`layer`  
Layer number.

`neuron`  
Neuron number.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_activation\_function\_layer</span>
-   <span
    class="function">fann\_set\_activation\_function\_hidden</span>
-   <span
    class="function">fann\_set\_activation\_function\_output</span>
-   <span class="function">fann\_set\_activation\_steepness</span>
-   <span class="function">fann\_get\_activation\_function</span>

fann\_set\_activation\_steepness\_hidden
========================================

Sets the steepness of the activation steepness for all neurons in the
all hidden layers

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_steepness\_hidden</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">float</span> `$activation_steepness`</span> )

Sets the steepness of the activation steepness for all neurons in the
all hidden layers.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_steepness`  
The activation steepness.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_activation\_steepness</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_layer</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_output</span>
-   <span class="function">fann\_get\_activation\_steepness</span>
-   <span class="function">fann\_set\_activation\_function</span>

fann\_set\_activation\_steepness\_layer
=======================================

Sets the activation steepness for all of the neurons in the supplied
layer number

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_steepness\_layer</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">float</span> `$activation_steepness`</span> , <span
class="methodparam"><span class="type">int</span> `$layer`</span> )

Set the activation steepness for all of the neurons in layer number
*layer*, counting the input layer as layer 0.

It is not possible to set activation steepness for the neurons in the
input layer.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_steepness`  
The activation steepness.

`layer`  
Layer number.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_activation\_steepness</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_hidden</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_output</span>
-   <span class="function">fann\_get\_activation\_steepness</span>
-   <span class="function">fann\_set\_activation\_function</span>

fann\_set\_activation\_steepness\_output
========================================

Sets the steepness of the activation steepness in the output layer

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_steepness\_output</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">float</span> `$activation_steepness`</span> )

Sets the steepness of the activation steepness in the output layer.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_steepness`  
The activation steepness.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_activation\_steepness</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_layer</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_hidden</span>
-   <span class="function">fann\_get\_activation\_steepness</span>
-   <span class="function">fann\_set\_activation\_function</span>

fann\_set\_activation\_steepness
================================

Sets the activation steepness for supplied neuron and layer number

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_activation\_steepness</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$activation_steepness`</span> , <span class="methodparam"><span
class="type">int</span> `$layer`</span> , <span
class="methodparam"><span class="type">int</span> `$neuron`</span> )

Set the activation steepness for neuron number *neuron* in layer number
*layer*, counting the input layer as layer 0.

It is not possible to set activation steepness for the neurons in the
input layer.

The steepness of an activation function says something about how fast
the activation function goes from the minimum to the maximum. A high
value for the activation function will also give a more agressive
training.

When training neural networks where the output values should be at the
extremes (usually 0 and 1, depending on the activation function), a
steep activation function can be used (e.g. 1.0).

The default activation steepness is 0.5.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`activation_steepness`  
The activation steepness.

`layer`  
Layer number.

`neuron`  
Neuron number.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_set\_activation\_steepness\_layer</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_hidden</span>
-   <span
    class="function">fann\_set\_activation\_steepness\_output</span>
-   <span class="function">fann\_get\_activation\_steepness</span>
-   <span class="function">fann\_set\_activation\_function</span>

fann\_set\_bit\_fail\_limit
===========================

Set the bit fail limit used during training

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_bit\_fail\_limit</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$bit_fail_limit`</span> )

Set the bit fail limit used during training.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`bit_fail_limit`  
The bit fail limit.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_bit\_fail\_limit</span>

fann\_set\_callback
===================

Sets the callback function for use during training

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_callback</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Sets the callback function for use during training. It means that it is
called from <span class="function">fann\_train\_on\_data</span> or <span
class="function">fann\_train\_on\_file</span>.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`callback`  
The supplied callback function takes following parameters:

-   *ann* - The neural network <span class="type">resource</span>
-   *train* - The train data <span class="type">resource</span> or
    **`NULL`** if called from <span
    class="function">fann\_train\_on\_file</span>
-   *max\_epochs* - The maximum number of epochs the training should
    continue
-   *epochs\_between\_reports* - The number of epochs between calling
    this function
-   *desired\_error* - The desired <span
    class="function">fann\_get\_MSE</span> or <span
    class="function">fann\_get\_bit\_fail</span>, depending on the stop
    function chosen by <span
    class="function">fann\_set\_train\_stop\_function</span>
-   *epochs* - The current epoch

The callback should return **`TRUE`**. If it returns **`FALSE`**, the
training will terminate.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_train\_on\_file</span>

fann\_set\_cascade\_activation\_functions
=========================================

Sets the array of cascade candidate activation functions

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_activation\_functions</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">array</span> `$cascade_activation_functions`</span> )

Sets the array of cascade candidate activation functions.

See <span class="function">fann\_get\_cascade\_num\_candidates</span>
for a description of which candidate neurons will be generated by this
array.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_activation_functions`  
The array of cascade candidate activation functions.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_get\_cascade\_activation\_functions\_count</span>
-   <span
    class="function">fann\_set\_cascade\_activation\_functions</span>

fann\_set\_cascade\_activation\_steepnesses
===========================================

Sets the array of cascade candidate activation steepnesses

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_activation\_steepnesses</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">array</span> `$cascade_activation_steepnesses_count`</span>
)

Sets the array of cascade candidate activation steepnesses.

See <span class="function">fann\_get\_cascade\_num\_candidates</span>
for a description of which candidate neurons will be generated by this
array.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_activation_steepnesses_count`  
The array of cascade candidate activation steepnesses.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_get\_cascade\_activation\_steepnesses</span>
-   <span
    class="function">fann\_get\_cascade\_activation\_steepnesses\_count</span>

fann\_set\_cascade\_candidate\_change\_fraction
===============================================

Sets the cascade candidate change fraction

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_candidate\_change\_fraction</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">float</span> `$cascade_candidate_change_fraction`</span> )

Sets the cascade candidate change fraction.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_candidate_change_fraction`  
The cascade candidate change fraction.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_get\_cascade\_candidate\_change\_fraction</span>

fann\_set\_cascade\_candidate\_limit
====================================

Sets the candidate limit

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_candidate\_limit</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$cascade_candidate_limit`</span> )

Sets the candidate limit.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_candidate_limit`  
The candidate limit.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_cascade\_candidate\_limit</span>

fann\_set\_cascade\_candidate\_stagnation\_epochs
=================================================

Sets the number of cascade candidate stagnation epochs

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_candidate\_stagnation\_epochs</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span class="type">int</span>
`$cascade_candidate_stagnation_epochs`</span> )

Sets the number of cascade candidate stagnation epochs.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_candidate_stagnation_epochs`  
The number of cascade candidate stagnation epochs.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_get\_cascade\_candidate\_stagnation\_epochs</span>

fann\_set\_cascade\_max\_cand\_epochs
=====================================

Sets the max candidate epochs

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_max\_cand\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$cascade_max_cand_epochs`</span> )

Sets the max candidate epochs.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_max_cand_epochs`  
The max candidate epochs.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_cascade\_max\_cand\_epochs</span>

fann\_set\_cascade\_max\_out\_epochs
====================================

Sets the maximum out epochs

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_max\_out\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$cascade_max_out_epochs`</span> )

Sets the maximum out epochs.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_max_out_epochs`  
The maximum out epochs.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_cascade\_max\_out\_epochs</span>

fann\_set\_cascade\_min\_cand\_epochs
=====================================

Sets the min candidate epochs

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_min\_cand\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$cascade_min_cand_epochs`</span> )

Sets the min candidate epochs.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_min_cand_epochs`  
The minimum candidate epochs.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_get\_cascade\_min\_cand\_epochs</span>

fann\_set\_cascade\_min\_out\_epochs
====================================

Sets the minimum out epochs

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_min\_out\_epochs</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$cascade_min_out_epochs`</span> )

Sets the minimum out epochs.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_min_out_epochs`  
The minimum out epochs.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_get\_cascade\_min\_out\_epochs</span>

fann\_set\_cascade\_num\_candidate\_groups
==========================================

Sets the number of candidate groups

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_num\_candidate\_groups</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span class="type">int</span>
`$cascade_num_candidate_groups`</span> )

Sets the number of candidate groups.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_num_candidate_groups`  
The number of candidate groups.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_get\_cascade\_num\_candidate\_groups</span>

fann\_set\_cascade\_output\_change\_fraction
============================================

Sets the cascade output change fraction

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_output\_change\_fraction</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">float</span> `$cascade_output_change_fraction`</span> )

Sets the cascade output change fraction.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_output_change_fraction`  
The cascade output change fraction.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_get\_cascade\_output\_change\_fraction</span>

fann\_set\_cascade\_output\_stagnation\_epochs
==============================================

Sets the number of cascade output stagnation epochs

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_output\_stagnation\_epochs</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span class="type">int</span>
`$cascade_output_stagnation_epochs`</span> )

Sets the number of cascade output stagnation epochs.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_output_stagnation_epochs`  
The number of cascade output stagnation epochs.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span
    class="function">fann\_get\_cascade\_output\_stagnation\_epochs</span>

fann\_set\_cascade\_weight\_multiplier
======================================

Sets the weight multiplier

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_cascade\_weight\_multiplier</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$cascade_weight_multiplier`</span> )

Sets the weight multiplier.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`cascade_weight_multiplier`  
The weight multiplier.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_cascade\_weight\_multiplier</span>

fann\_set\_error\_log
=====================

Sets where the errors are logged to

### Description

<span class="type">void</span> <span
class="methodname">fann\_set\_error\_log</span> ( <span
class="methodparam"><span class="type">resource</span> `$errdat`</span>
, <span class="methodparam"><span class="type">string</span>
`$log_file`</span> )

Sets where the errors are logged to.

### Parameters

`errdat`  
Either neural network <span class="type">resource</span> or neural
network trainining data <span class="type">resource</span>.

`log_file`  
The log file path.

### Return Values

No value is returned.

fann\_set\_input\_scaling\_params
=================================

Calculate input scaling parameters for future use based on training data

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_input\_scaling\_params</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$train_data`</span> , <span class="methodparam"><span
class="type">float</span> `$new_input_min`</span> , <span
class="methodparam"><span class="type">float</span>
`$new_input_max`</span> )

Calculate input scaling parameters for future use based on training
data.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`train_data`  
Neural network training data <span class="type">resource</span>.

`new_input_min`  
The desired lower bound in input data after scaling (not strictly
followed)

`new_input_max`  
The desired upper bound in input data after scaling (not strictly
followed)

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_output\_scaling\_params</span>

fann\_set\_learning\_momentum
=============================

Sets the learning momentum

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_learning\_momentum</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$learning_momentum`</span> )

Sets the learning momentum.

More info available in <span
class="function">fann\_get\_learning\_momentum</span>.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`learning_momentum`  
The learning momentum.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_learning\_momentum</span>
-   <span class="function">fann\_set\_training\_algorithm</span>

fann\_set\_learning\_rate
=========================

Sets the learning rate

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_learning\_rate</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$learning_rate`</span> )

Sets the learning rate.

More info available in <span
class="function">fann\_get\_learning\_rate</span>.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`learning_rate`  
The learning rate.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_learning\_rate</span>
-   <span class="function">fann\_set\_training\_algorithm</span>

fann\_set\_output\_scaling\_params
==================================

Calculate output scaling parameters for future use based on training
data

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_output\_scaling\_params</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$train_data`</span> , <span class="methodparam"><span
class="type">float</span> `$new_output_min`</span> , <span
class="methodparam"><span class="type">float</span>
`$new_output_max`</span> )

Calculate output scaling parameters for future use based on training
data.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`train_data`  
Neural network training data <span class="type">resource</span>.

`new_output_min`  
The desired lower bound in output data after scaling (not strictly
followed)

`new_output_max`  
The desired upper bound in output data after scaling (not strictly
followed)

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_input\_scaling\_params</span>

fann\_set\_quickprop\_decay
===========================

Sets the quickprop decay factor

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_quickprop\_decay</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$quickprop_decay`</span> )

Sets the quickprop decay factor.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`quickprop_decay`  
The quickprop decay factor.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_quickprop\_decay</span>

fann\_set\_quickprop\_mu
========================

Sets the quickprop mu factor

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_quickprop\_mu</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$quickprop_mu`</span> )

Sets the quickprop mu factor.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`quickprop_mu`  
The mu factor.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_quickprop\_mu</span>

fann\_set\_rprop\_decrease\_factor
==================================

Sets the decrease factor used during RPROP training

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_rprop\_decrease\_factor</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$rprop_decrease_factor`</span> )

Sets the decrease factor used during RPROP training.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`rprop_decrease_factor`  
The decrease factor.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_rprop\_decrease\_factor</span>

fann\_set\_rprop\_delta\_max
============================

Sets the maximum step-size

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_rprop\_delta\_max</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$rprop_delta_max`</span> )

The maximum step-size is a positive number determining how large the
maximum step-size may be.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`rprop_delta_max`  
The maximum step-size.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_rprop\_delta\_max</span>
-   <span class="function">fann\_get\_rprop\_delta\_min</span>

fann\_set\_rprop\_delta\_min
============================

Sets the minimum step-size

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_rprop\_delta\_min</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$rprop_delta_min`</span> )

The minimum step-size is a small positive number determining how small
the minimum step-size may be.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`rprop_delta_min`  
The minimum step-size.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_rprop\_delta\_min</span>

fann\_set\_rprop\_delta\_zero
=============================

Sets the initial step-size

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_rprop\_delta\_zero</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$rprop_delta_zero`</span> )

The initial step-size is a positive number determining the initial step
size.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`rprop_delta_zero`  
The initial step-size.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_rprop\_delta\_zero</span>
-   <span class="function">fann\_get\_rprop\_delta\_min</span>
-   <span class="function">fann\_get\_rprop\_delta\_max</span>

fann\_set\_rprop\_increase\_factor
==================================

Sets the increase factor used during RPROP training

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_rprop\_increase\_factor</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$rprop_increase_factor`</span> )

Sets the increase factor used during RPROP training.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`rprop_increase_factor`  
The increase factor.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_rprop\_increase\_factor</span>

fann\_set\_sarprop\_step\_error\_shift
======================================

Sets the sarprop step error shift

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_sarprop\_step\_error\_shift</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sarprop_step_error_shift`</span> )

Sets the sarprop step error shift.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`sarprop_step_error_shift`  
The sarprop step error shift.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_get\_sarprop\_step\_error\_shift</span>

fann\_set\_sarprop\_step\_error\_threshold\_factor
==================================================

Sets the sarprop step error threshold factor

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_sarprop\_step\_error\_threshold\_factor</span>
( <span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">float</span> `$sarprop_step_error_threshold_factor`</span>
)

Sets the sarprop step error threshold factor.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`sarprop_step_error_threshold_factor`  
The sarprop step error threshold factor.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span
    class="function">fann\_get\_sarprop\_step\_error\_threshold\_factor</span>

fann\_set\_sarprop\_temperature
===============================

Sets the sarprop temperature

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_sarprop\_temperature</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sarprop_temperature`</span> )

Sets the sarprop temperature.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`sarprop_temperature`  
The sarprop temperature.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span class="function">fann\_get\_sarprop\_temperature</span>

fann\_set\_sarprop\_weight\_decay\_shift
========================================

Sets the sarprop weight decay shift

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_sarprop\_weight\_decay\_shift</span> (
<span class="methodparam"><span class="type">resource</span>
`$ann`</span> , <span class="methodparam"><span
class="type">float</span> `$sarprop_weight_decay_shift`</span> )

Sets the sarprop weight decay shift.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`sarprop_weight_decay_shift`  
The sarprop weight decay shift.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Notes

> **Note**:
>
> This function is only available if the fann extension has been build
> against libfann \>= 2.2.

### See Also

-   <span
    class="function">fann\_get\_sarprop\_weight\_decay\_shift</span>

fann\_set\_scaling\_params
==========================

Calculate input and output scaling parameters for future use based on
training data

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_scaling\_params</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$train_data`</span> , <span class="methodparam"><span
class="type">float</span> `$new_input_min`</span> , <span
class="methodparam"><span class="type">float</span>
`$new_input_max`</span> , <span class="methodparam"><span
class="type">float</span> `$new_output_min`</span> , <span
class="methodparam"><span class="type">float</span>
`$new_output_max`</span> )

Calculate input and output scaling parameters for future use based on
training data.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`train_data`  
Neural network training data <span class="type">resource</span>.

`new_input_min`  
The desired lower bound in input data after scaling (not strictly
followed)

`new_input_max`  
The desired upper bound in input data after scaling (not strictly
followed)

`new_output_min`  
The desired lower bound in output data after scaling (not strictly
followed)

`new_output_max`  
The desired upper bound in output data after scaling (not strictly
followed)

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_set\_input\_scaling\_params</span>
-   <span class="function">fann\_set\_output\_scaling\_params</span>

fann\_set\_train\_error\_function
=================================

Sets the error function used during training

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_train\_error\_function</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$error_function`</span> )

Sets the error function used during training.

The error functions are described further in
<a href="/fann/constants.html#Error%20function%20used%20during%20training" class="link">error functions</a>
constants.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`error_function`  
The
<a href="/fann/constants.html#Error%20function%20used%20during%20training" class="link">error function</a>
constant

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_train\_error\_function</span>

fann\_set\_train\_stop\_function
================================

Sets the stop function used during training

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_train\_stop\_function</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$stop_function`</span> )

Sets the stop function used during training.

The stop functions are described further in
<a href="/fann/constants.html#Stop%20criteria%20used%20during%20training" class="link">stop functions</a>
constants.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`stop_function`  
The
<a href="/fann/constants.html#Stop%20criteria%20used%20during%20training" class="link">stop function</a>
constant.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_train\_stop\_function</span>

fann\_set\_training\_algorithm
==============================

Sets the training algorithm

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_training\_algorithm</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$training_algorithm`</span> )

Sets the training algorithm.

More info available in <span
class="function">fann\_get\_training\_algorithm</span>.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`training_algorithm`  
<a href="/fann/constants.html#Training%20algorithms" class="link">Training algorithm</a>
constant

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_get\_training\_algorithm</span>

fann\_set\_weight\_array
========================

Set connections in the network

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_weight\_array</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">array</span>
`$connections`</span> )

Set connections in the network.

Only the weights can be changed, connections and weights are ignored if
they do not already exist in the network.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`connections`  
An array of <span class="classname">FANNConnection</span> objects

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

fann\_set\_weight
=================

Set a connection in the network

### Description

<span class="type">bool</span> <span
class="methodname">fann\_set\_weight</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">int</span>
`$from_neuron`</span> , <span class="methodparam"><span
class="type">int</span> `$to_neuron`</span> , <span
class="methodparam"><span class="type">float</span> `$weight`</span> )

Set a connections in the network.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`from_neuron`  
The neuron where the connection starts

`to_neuron`  
The neuron where the connection ends

`weight`  
Connection weight

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

fann\_shuffle\_train\_data
==========================

Shuffles training data, randomizing the order

### Description

<span class="type">bool</span> <span
class="methodname">fann\_shuffle\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span>
`$train_data`</span> )

Shuffles training data, randomizing the order. This is recommended for
incremental training, while it have no influence during batch training.

### Parameters

`train_data`  
Neural network training data <span class="type">resource</span>.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

fann\_subset\_train\_data
=========================

Returns an copy of a subset of the train data

### Description

<span class="type">resource</span> <span
class="methodname">fann\_subset\_train\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$data`</span> ,
<span class="methodparam"><span class="type">int</span> `$pos`</span> ,
<span class="methodparam"><span class="type">int</span> `$length`</span>
)

Returns an copy of a subset of the train data <span
class="type">resource</span>, starting at position *pos* and *length*
elements forward.

The *fann\_subset\_train\_data(train\_data, 0,
fann\_length\_train\_data(train\_data))* do the same as <span
class="function">fann\_duplicate\_train\_data</span>

### Parameters

`data`  
Neural network training data <span class="type">resource</span>.

`pos`  
Starting position.

`length`  
The number of copied elements.

### Return Values

Returns a train data <span class="type">resource</span> on success, or
**`FALSE`** on error.

### See Also

-   <span class="function">fann\_duplicate\_train\_data</span>

fann\_test\_data
================

Test a set of training data and calculates the MSE for the training data

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_test\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$data`</span> )

Test a set of training data and calculates the MSE for the training
data.

This function updates the MSE and the bit fail values.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`data`  
Neural network training data <span class="type">resource</span>.

### Return Values

The updated MSE, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_train\_epoch</span>
-   <span class="function">fann\_get\_bit\_fail</span>
-   <span class="function">fann\_get\_MSE</span>
-   <span class="function">fann\_set\_training\_algorithm</span>

fann\_test
==========

Test with a set of inputs, and a set of desired outputs

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">fann\_test</span> ( <span class="methodparam"><span
class="type">resource</span> `$ann`</span> , <span
class="methodparam"><span class="type">array</span> `$input`</span> ,
<span class="methodparam"><span class="type">array</span>
`$desired_output`</span> )

Test with a set of inputs, and a set of desired outputs. This operation
updates the mean square error, but does not change the network in any
way.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`input`  
An array of inputs. This array must be exactly <span
class="function">fann\_get\_num\_input</span> long.

`desired_output`  
An array of desired outputs. This array must be exactly <span
class="function">fann\_get\_num\_output</span> long.

### Return Values

Returns test outputs on success, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_test\_data</span>
-   <span class="function">fann\_train</span>
-   <span class="function">fann\_get\_num\_input</span>
-   <span class="function">fann\_get\_num\_output</span>

fann\_train\_epoch
==================

Train one epoch with a set of training data

### Description

<span class="type"><span class="type">float</span><span
class="type">false</span></span> <span
class="methodname">fann\_train\_epoch</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$data`</span> )

Train one epoch with the training data stored in data. One epoch is
where all of the training data is considered exactly once.

This function returns the MSE error as it is calculated either before or
during the actual training. This is not the actual MSE after the
training epoch, but since calculating this will require to go through
the entire training set once more. It is more than adequate to use this
value during training.

The training algorithm used by this function is chosen by <span
class="function">fann\_set\_training\_algorithm</span> function.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`data`  
Neural network training data <span class="type">resource</span>.

### Return Values

The MSE, or **`FALSE`** on error.

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_test\_data</span>
-   <span class="function">fann\_get\_MSE</span>
-   <span class="function">fann\_set\_training\_algorithm</span>

fann\_train\_on\_data
=====================

Trains on an entire dataset for a period of time

### Description

<span class="type">bool</span> <span
class="methodname">fann\_train\_on\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$max_epochs`</span> , <span class="methodparam"><span
class="type">int</span> `$epochs_between_reports`</span> , <span
class="methodparam"><span class="type">float</span>
`$desired_error`</span> )

Trains on an entire dataset for a period of time.

This training uses the training algorithm chosen by <span
class="function">fann\_set\_training\_algorithm</span> and the
parameters set for these training algorithms.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`data`  
Neural network training data <span class="type">resource</span>.

`max_epochs`  
The maximum number of epochs the training should continue

`epochs_between_reports`  
The number of epochs between calling a callback function. A value of
zero means that user function is not called.

`desired_error`  
The desired <span class="function">fann\_get\_MSE</span> or <span
class="function">fann\_get\_bit\_fail</span>, depending on the stop
function chosen by <span
class="function">fann\_set\_train\_stop\_function</span>

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_train\_on\_file</span>
-   <span class="function">fann\_train\_epoch</span>
-   <span class="function">fann\_get\_bit\_fail</span>
-   <span class="function">fann\_get\_MSE</span>
-   <span class="function">fann\_set\_train\_stop\_function</span>
-   <span class="function">fann\_set\_training\_algorithm</span>
-   <span class="function">fann\_set\_callback</span>

fann\_train\_on\_file
=====================

Trains on an entire dataset, which is read from file, for a period of
time

### Description

<span class="type">bool</span> <span
class="methodname">fann\_train\_on\_file</span> ( <span
class="methodparam"><span class="type">resource</span> `$ann`</span> ,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">int</span> `$max_epochs`</span> , <span
class="methodparam"><span class="type">int</span>
`$epochs_between_reports`</span> , <span class="methodparam"><span
class="type">float</span> `$desired_error`</span> )

Trains on an entire dataset, which is read from file, for a period of
time.

This training uses the training algorithm chosen by <span
class="function">fann\_set\_training\_algorithm</span> and the
parameters set for these training algorithms.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`filename`  
The file containing train data

`max_epochs`  
The maximum number of epochs the training should continue

`epochs_between_reports`  
The number of epochs between calling a user function. A value of zero
means that user function is not called.

`desired_error`  
The desired <span class="function">fann\_get\_MSE</span> or <span
class="function">fann\_get\_bit\_fail</span>, depending on the stop
function chosen by <span
class="function">fann\_set\_train\_stop\_function</span>

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_train\_epoch</span>
-   <span class="function">fann\_get\_bit\_fail</span>
-   <span class="function">fann\_get\_MSE</span>
-   <span class="function">fann\_set\_train\_stop\_function</span>
-   <span class="function">fann\_set\_training\_algorithm</span>
-   <span class="function">fann\_set\_callback</span>

fann\_train
===========

Train one iteration with a set of inputs, and a set of desired outputs

### Description

<span class="type">bool</span> <span
class="methodname">fann\_train</span> ( <span class="methodparam"><span
class="type">resource</span> `$ann`</span> , <span
class="methodparam"><span class="type">array</span> `$input`</span> ,
<span class="methodparam"><span class="type">array</span>
`$desired_output`</span> )

Train one iteration with a set of inputs, and a set of desired outputs.
This training is always incremental training, since only one pattern is
presented.

### Parameters

`ann`  
Neural network <span class="type">resource</span>.

`input`  
An array of inputs. This array must be exactly <span
class="function">fann\_get\_num\_input</span> long.

`desired_output`  
An array of desired outputs. This array must be exactly <span
class="function">fann\_get\_num\_output</span> long.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### See Also

-   <span class="function">fann\_train\_on\_data</span>
-   <span class="function">fann\_train\_epoch</span>
-   <span class="function">fann\_get\_num\_input</span>
-   <span class="function">fann\_get\_num\_output</span>

**Table of Contents**

-   [fann\_cascadetrain\_on\_data](/ref/fann.html#fann_cascadetrain_on_data)
    — Trains on an entire dataset, for a period of time using the
    Cascade2 training algorithm
-   [fann\_cascadetrain\_on\_file](/ref/fann.html#fann_cascadetrain_on_file)
    — Trains on an entire dataset read from file, for a period of time
    using the Cascade2 training algorithm
-   [fann\_clear\_scaling\_params](/ref/fann.html#fann_clear_scaling_params)
    — Clears scaling parameters
-   [fann\_copy](/ref/fann.html#fann_copy) — Creates a copy of a fann
    structure
-   [fann\_create\_from\_file](/ref/fann.html#fann_create_from_file) —
    Constructs a backpropagation neural network from a configuration
    file
-   [fann\_create\_shortcut\_array](/ref/fann.html#fann_create_shortcut_array)
    — Creates a standard backpropagation neural network which is not
    fully connectected and has shortcut connections
-   [fann\_create\_shortcut](/ref/fann.html#fann_create_shortcut) —
    Creates a standard backpropagation neural network which is not fully
    connectected and has shortcut connections
-   [fann\_create\_sparse\_array](/ref/fann.html#fann_create_sparse_array)
    — Creates a standard backpropagation neural network, which is not
    fully connected using an array of layer sizes
-   [fann\_create\_sparse](/ref/fann.html#fann_create_sparse) — Creates
    a standard backpropagation neural network, which is not fully
    connected
-   [fann\_create\_standard\_array](/ref/fann.html#fann_create_standard_array)
    — Creates a standard fully connected backpropagation neural network
    using an array of layer sizes
-   [fann\_create\_standard](/ref/fann.html#fann_create_standard) —
    Creates a standard fully connected backpropagation neural network
-   [fann\_create\_train\_from\_callback](/ref/fann.html#fann_create_train_from_callback)
    — Creates the training data struct from a user supplied function
-   [fann\_create\_train](/ref/fann.html#fann_create_train) — Creates an
    empty training data struct
-   [fann\_descale\_input](/ref/fann.html#fann_descale_input) — Scale
    data in input vector after get it from ann based on previously
    calculated parameters
-   [fann\_descale\_output](/ref/fann.html#fann_descale_output) — Scale
    data in output vector after get it from ann based on previously
    calculated parameters
-   [fann\_descale\_train](/ref/fann.html#fann_descale_train) — Descale
    input and output data based on previously calculated parameters
-   [fann\_destroy\_train](/ref/fann.html#fann_destroy_train) —
    Destructs the training data
-   [fann\_destroy](/ref/fann.html#fann_destroy) — Destroys the entire
    network and properly freeing all the associated memory
-   [fann\_duplicate\_train\_data](/ref/fann.html#fann_duplicate_train_data)
    — Returns an exact copy of a fann train data
-   [fann\_get\_activation\_function](/ref/fann.html#fann_get_activation_function)
    — Returns the activation function
-   [fann\_get\_activation\_steepness](/ref/fann.html#fann_get_activation_steepness)
    — Returns the activation steepness for supplied neuron and layer
    number
-   [fann\_get\_bias\_array](/ref/fann.html#fann_get_bias_array) — Get
    the number of bias in each layer in the network
-   [fann\_get\_bit\_fail\_limit](/ref/fann.html#fann_get_bit_fail_limit)
    — Returns the bit fail limit used during training
-   [fann\_get\_bit\_fail](/ref/fann.html#fann_get_bit_fail) — The
    number of fail bits
-   [fann\_get\_cascade\_activation\_functions\_count](/ref/fann.html#fann_get_cascade_activation_functions_count)
    — Returns the number of cascade activation functions
-   [fann\_get\_cascade\_activation\_functions](/ref/fann.html#fann_get_cascade_activation_functions)
    — Returns the cascade activation functions
-   [fann\_get\_cascade\_activation\_steepnesses\_count](/ref/fann.html#fann_get_cascade_activation_steepnesses_count)
    — The number of activation steepnesses
-   [fann\_get\_cascade\_activation\_steepnesses](/ref/fann.html#fann_get_cascade_activation_steepnesses)
    — Returns the cascade activation steepnesses
-   [fann\_get\_cascade\_candidate\_change\_fraction](/ref/fann.html#fann_get_cascade_candidate_change_fraction)
    — Returns the cascade candidate change fraction
-   [fann\_get\_cascade\_candidate\_limit](/ref/fann.html#fann_get_cascade_candidate_limit)
    — Return the candidate limit
-   [fann\_get\_cascade\_candidate\_stagnation\_epochs](/ref/fann.html#fann_get_cascade_candidate_stagnation_epochs)
    — Returns the number of cascade candidate stagnation epochs
-   [fann\_get\_cascade\_max\_cand\_epochs](/ref/fann.html#fann_get_cascade_max_cand_epochs)
    — Returns the maximum candidate epochs
-   [fann\_get\_cascade\_max\_out\_epochs](/ref/fann.html#fann_get_cascade_max_out_epochs)
    — Returns the maximum out epochs
-   [fann\_get\_cascade\_min\_cand\_epochs](/ref/fann.html#fann_get_cascade_min_cand_epochs)
    — Returns the minimum candidate epochs
-   [fann\_get\_cascade\_min\_out\_epochs](/ref/fann.html#fann_get_cascade_min_out_epochs)
    — Returns the minimum out epochs
-   [fann\_get\_cascade\_num\_candidate\_groups](/ref/fann.html#fann_get_cascade_num_candidate_groups)
    — Returns the number of candidate groups
-   [fann\_get\_cascade\_num\_candidates](/ref/fann.html#fann_get_cascade_num_candidates)
    — Returns the number of candidates used during training
-   [fann\_get\_cascade\_output\_change\_fraction](/ref/fann.html#fann_get_cascade_output_change_fraction)
    — Returns the cascade output change fraction
-   [fann\_get\_cascade\_output\_stagnation\_epochs](/ref/fann.html#fann_get_cascade_output_stagnation_epochs)
    — Returns the number of cascade output stagnation epochs
-   [fann\_get\_cascade\_weight\_multiplier](/ref/fann.html#fann_get_cascade_weight_multiplier)
    — Returns the weight multiplier
-   [fann\_get\_connection\_array](/ref/fann.html#fann_get_connection_array)
    — Get connections in the network
-   [fann\_get\_connection\_rate](/ref/fann.html#fann_get_connection_rate)
    — Get the connection rate used when the network was created
-   [fann\_get\_errno](/ref/fann.html#fann_get_errno) — Returns the last
    error number
-   [fann\_get\_errstr](/ref/fann.html#fann_get_errstr) — Returns the
    last errstr
-   [fann\_get\_layer\_array](/ref/fann.html#fann_get_layer_array) — Get
    the number of neurons in each layer in the network
-   [fann\_get\_learning\_momentum](/ref/fann.html#fann_get_learning_momentum)
    — Returns the learning momentum
-   [fann\_get\_learning\_rate](/ref/fann.html#fann_get_learning_rate) —
    Returns the learning rate
-   [fann\_get\_MSE](/ref/fann.html#fann_get_MSE) — Reads the mean
    square error from the network
-   [fann\_get\_network\_type](/ref/fann.html#fann_get_network_type) —
    Get the type of neural network it was created as
-   [fann\_get\_num\_input](/ref/fann.html#fann_get_num_input) — Get the
    number of input neurons
-   [fann\_get\_num\_layers](/ref/fann.html#fann_get_num_layers) — Get
    the number of layers in the neural network
-   [fann\_get\_num\_output](/ref/fann.html#fann_get_num_output) — Get
    the number of output neurons
-   [fann\_get\_quickprop\_decay](/ref/fann.html#fann_get_quickprop_decay)
    — Returns the decay which is a factor that weights should decrease
    in each iteration during quickprop training
-   [fann\_get\_quickprop\_mu](/ref/fann.html#fann_get_quickprop_mu) —
    Returns the mu factor
-   [fann\_get\_rprop\_decrease\_factor](/ref/fann.html#fann_get_rprop_decrease_factor)
    — Returns the increase factor used during RPROP training
-   [fann\_get\_rprop\_delta\_max](/ref/fann.html#fann_get_rprop_delta_max)
    — Returns the maximum step-size
-   [fann\_get\_rprop\_delta\_min](/ref/fann.html#fann_get_rprop_delta_min)
    — Returns the minimum step-size
-   [fann\_get\_rprop\_delta\_zero](/ref/fann.html#fann_get_rprop_delta_zero)
    — Returns the initial step-size
-   [fann\_get\_rprop\_increase\_factor](/ref/fann.html#fann_get_rprop_increase_factor)
    — Returns the increase factor used during RPROP training
-   [fann\_get\_sarprop\_step\_error\_shift](/ref/fann.html#fann_get_sarprop_step_error_shift)
    — Returns the sarprop step error shift
-   [fann\_get\_sarprop\_step\_error\_threshold\_factor](/ref/fann.html#fann_get_sarprop_step_error_threshold_factor)
    — Returns the sarprop step error threshold factor
-   [fann\_get\_sarprop\_temperature](/ref/fann.html#fann_get_sarprop_temperature)
    — Returns the sarprop temperature
-   [fann\_get\_sarprop\_weight\_decay\_shift](/ref/fann.html#fann_get_sarprop_weight_decay_shift)
    — Returns the sarprop weight decay shift
-   [fann\_get\_total\_connections](/ref/fann.html#fann_get_total_connections)
    — Get the total number of connections in the entire network
-   [fann\_get\_total\_neurons](/ref/fann.html#fann_get_total_neurons) —
    Get the total number of neurons in the entire network
-   [fann\_get\_train\_error\_function](/ref/fann.html#fann_get_train_error_function)
    — Returns the error function used during training
-   [fann\_get\_train\_stop\_function](/ref/fann.html#fann_get_train_stop_function)
    — Returns the stop function used during training
-   [fann\_get\_training\_algorithm](/ref/fann.html#fann_get_training_algorithm)
    — Returns the training algorithm
-   [fann\_init\_weights](/ref/fann.html#fann_init_weights) — Initialize
    the weights using Widrow + Nguyen’s algorithm
-   [fann\_length\_train\_data](/ref/fann.html#fann_length_train_data) —
    Returns the number of training patterns in the train data
-   [fann\_merge\_train\_data](/ref/fann.html#fann_merge_train_data) —
    Merges the train data
-   [fann\_num\_input\_train\_data](/ref/fann.html#fann_num_input_train_data)
    — Returns the number of inputs in each of the training patterns in
    the train data
-   [fann\_num\_output\_train\_data](/ref/fann.html#fann_num_output_train_data)
    — Returns the number of outputs in each of the training patterns in
    the train data
-   [fann\_print\_error](/ref/fann.html#fann_print_error) — Prints the
    error string
-   [fann\_randomize\_weights](/ref/fann.html#fann_randomize_weights) —
    Give each connection a random weight between min\_weight and
    max\_weight
-   [fann\_read\_train\_from\_file](/ref/fann.html#fann_read_train_from_file)
    — Reads a file that stores training data
-   [fann\_reset\_errno](/ref/fann.html#fann_reset_errno) — Resets the
    last error number
-   [fann\_reset\_errstr](/ref/fann.html#fann_reset_errstr) — Resets the
    last error string
-   [fann\_reset\_MSE](/ref/fann.html#fann_reset_MSE) — Resets the mean
    square error from the network
-   [fann\_run](/ref/fann.html#fann_run) — Will run input through the
    neural network
-   [fann\_save\_train](/ref/fann.html#fann_save_train) — Save the
    training structure to a file
-   [fann\_save](/ref/fann.html#fann_save) — Saves the entire network to
    a configuration file
-   [fann\_scale\_input\_train\_data](/ref/fann.html#fann_scale_input_train_data)
    — Scales the inputs in the training data to the specified range
-   [fann\_scale\_input](/ref/fann.html#fann_scale_input) — Scale data
    in input vector before feed it to ann based on previously calculated
    parameters
-   [fann\_scale\_output\_train\_data](/ref/fann.html#fann_scale_output_train_data)
    — Scales the outputs in the training data to the specified range
-   [fann\_scale\_output](/ref/fann.html#fann_scale_output) — Scale data
    in output vector before feed it to ann based on previously
    calculated parameters
-   [fann\_scale\_train\_data](/ref/fann.html#fann_scale_train_data) —
    Scales the inputs and outputs in the training data to the specified
    range
-   [fann\_scale\_train](/ref/fann.html#fann_scale_train) — Scale input
    and output data based on previously calculated parameters
-   [fann\_set\_activation\_function\_hidden](/ref/fann.html#fann_set_activation_function_hidden)
    — Sets the activation function for all of the hidden layers
-   [fann\_set\_activation\_function\_layer](/ref/fann.html#fann_set_activation_function_layer)
    — Sets the activation function for all the neurons in the supplied
    layer
-   [fann\_set\_activation\_function\_output](/ref/fann.html#fann_set_activation_function_output)
    — Sets the activation function for the output layer
-   [fann\_set\_activation\_function](/ref/fann.html#fann_set_activation_function)
    — Sets the activation function for supplied neuron and layer
-   [fann\_set\_activation\_steepness\_hidden](/ref/fann.html#fann_set_activation_steepness_hidden)
    — Sets the steepness of the activation steepness for all neurons in
    the all hidden layers
-   [fann\_set\_activation\_steepness\_layer](/ref/fann.html#fann_set_activation_steepness_layer)
    — Sets the activation steepness for all of the neurons in the
    supplied layer number
-   [fann\_set\_activation\_steepness\_output](/ref/fann.html#fann_set_activation_steepness_output)
    — Sets the steepness of the activation steepness in the output layer
-   [fann\_set\_activation\_steepness](/ref/fann.html#fann_set_activation_steepness)
    — Sets the activation steepness for supplied neuron and layer number
-   [fann\_set\_bit\_fail\_limit](/ref/fann.html#fann_set_bit_fail_limit)
    — Set the bit fail limit used during training
-   [fann\_set\_callback](/ref/fann.html#fann_set_callback) — Sets the
    callback function for use during training
-   [fann\_set\_cascade\_activation\_functions](/ref/fann.html#fann_set_cascade_activation_functions)
    — Sets the array of cascade candidate activation functions
-   [fann\_set\_cascade\_activation\_steepnesses](/ref/fann.html#fann_set_cascade_activation_steepnesses)
    — Sets the array of cascade candidate activation steepnesses
-   [fann\_set\_cascade\_candidate\_change\_fraction](/ref/fann.html#fann_set_cascade_candidate_change_fraction)
    — Sets the cascade candidate change fraction
-   [fann\_set\_cascade\_candidate\_limit](/ref/fann.html#fann_set_cascade_candidate_limit)
    — Sets the candidate limit
-   [fann\_set\_cascade\_candidate\_stagnation\_epochs](/ref/fann.html#fann_set_cascade_candidate_stagnation_epochs)
    — Sets the number of cascade candidate stagnation epochs
-   [fann\_set\_cascade\_max\_cand\_epochs](/ref/fann.html#fann_set_cascade_max_cand_epochs)
    — Sets the max candidate epochs
-   [fann\_set\_cascade\_max\_out\_epochs](/ref/fann.html#fann_set_cascade_max_out_epochs)
    — Sets the maximum out epochs
-   [fann\_set\_cascade\_min\_cand\_epochs](/ref/fann.html#fann_set_cascade_min_cand_epochs)
    — Sets the min candidate epochs
-   [fann\_set\_cascade\_min\_out\_epochs](/ref/fann.html#fann_set_cascade_min_out_epochs)
    — Sets the minimum out epochs
-   [fann\_set\_cascade\_num\_candidate\_groups](/ref/fann.html#fann_set_cascade_num_candidate_groups)
    — Sets the number of candidate groups
-   [fann\_set\_cascade\_output\_change\_fraction](/ref/fann.html#fann_set_cascade_output_change_fraction)
    — Sets the cascade output change fraction
-   [fann\_set\_cascade\_output\_stagnation\_epochs](/ref/fann.html#fann_set_cascade_output_stagnation_epochs)
    — Sets the number of cascade output stagnation epochs
-   [fann\_set\_cascade\_weight\_multiplier](/ref/fann.html#fann_set_cascade_weight_multiplier)
    — Sets the weight multiplier
-   [fann\_set\_error\_log](/ref/fann.html#fann_set_error_log) — Sets
    where the errors are logged to
-   [fann\_set\_input\_scaling\_params](/ref/fann.html#fann_set_input_scaling_params)
    — Calculate input scaling parameters for future use based on
    training data
-   [fann\_set\_learning\_momentum](/ref/fann.html#fann_set_learning_momentum)
    — Sets the learning momentum
-   [fann\_set\_learning\_rate](/ref/fann.html#fann_set_learning_rate) —
    Sets the learning rate
-   [fann\_set\_output\_scaling\_params](/ref/fann.html#fann_set_output_scaling_params)
    — Calculate output scaling parameters for future use based on
    training data
-   [fann\_set\_quickprop\_decay](/ref/fann.html#fann_set_quickprop_decay)
    — Sets the quickprop decay factor
-   [fann\_set\_quickprop\_mu](/ref/fann.html#fann_set_quickprop_mu) —
    Sets the quickprop mu factor
-   [fann\_set\_rprop\_decrease\_factor](/ref/fann.html#fann_set_rprop_decrease_factor)
    — Sets the decrease factor used during RPROP training
-   [fann\_set\_rprop\_delta\_max](/ref/fann.html#fann_set_rprop_delta_max)
    — Sets the maximum step-size
-   [fann\_set\_rprop\_delta\_min](/ref/fann.html#fann_set_rprop_delta_min)
    — Sets the minimum step-size
-   [fann\_set\_rprop\_delta\_zero](/ref/fann.html#fann_set_rprop_delta_zero)
    — Sets the initial step-size
-   [fann\_set\_rprop\_increase\_factor](/ref/fann.html#fann_set_rprop_increase_factor)
    — Sets the increase factor used during RPROP training
-   [fann\_set\_sarprop\_step\_error\_shift](/ref/fann.html#fann_set_sarprop_step_error_shift)
    — Sets the sarprop step error shift
-   [fann\_set\_sarprop\_step\_error\_threshold\_factor](/ref/fann.html#fann_set_sarprop_step_error_threshold_factor)
    — Sets the sarprop step error threshold factor
-   [fann\_set\_sarprop\_temperature](/ref/fann.html#fann_set_sarprop_temperature)
    — Sets the sarprop temperature
-   [fann\_set\_sarprop\_weight\_decay\_shift](/ref/fann.html#fann_set_sarprop_weight_decay_shift)
    — Sets the sarprop weight decay shift
-   [fann\_set\_scaling\_params](/ref/fann.html#fann_set_scaling_params)
    — Calculate input and output scaling parameters for future use based
    on training data
-   [fann\_set\_train\_error\_function](/ref/fann.html#fann_set_train_error_function)
    — Sets the error function used during training
-   [fann\_set\_train\_stop\_function](/ref/fann.html#fann_set_train_stop_function)
    — Sets the stop function used during training
-   [fann\_set\_training\_algorithm](/ref/fann.html#fann_set_training_algorithm)
    — Sets the training algorithm
-   [fann\_set\_weight\_array](/ref/fann.html#fann_set_weight_array) —
    Set connections in the network
-   [fann\_set\_weight](/ref/fann.html#fann_set_weight) — Set a
    connection in the network
-   [fann\_shuffle\_train\_data](/ref/fann.html#fann_shuffle_train_data)
    — Shuffles training data, randomizing the order
-   [fann\_subset\_train\_data](/ref/fann.html#fann_subset_train_data) —
    Returns an copy of a subset of the train data
-   [fann\_test\_data](/ref/fann.html#fann_test_data) — Test a set of
    training data and calculates the MSE for the training data
-   [fann\_test](/ref/fann.html#fann_test) — Test with a set of inputs,
    and a set of desired outputs
-   [fann\_train\_epoch](/ref/fann.html#fann_train_epoch) — Train one
    epoch with a set of training data
-   [fann\_train\_on\_data](/ref/fann.html#fann_train_on_data) — Trains
    on an entire dataset for a period of time
-   [fann\_train\_on\_file](/ref/fann.html#fann_train_on_file) — Trains
    on an entire dataset, which is read from file, for a period of time
-   [fann\_train](/ref/fann.html#fann_train) — Train one iteration with
    a set of inputs, and a set of desired outputs

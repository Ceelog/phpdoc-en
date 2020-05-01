FANN (Fast Artificial Neural Network)
=====================================

**Table of Contents**

-   [Introduction](/intro/fann.html)
-   [Installing/Configuring](/fann/setup.html)
    -   [Requirements](/fann/setup.html#Requirements)
    -   [Installation](/fann/setup.html#Installation)
    -   [Runtime
        Configuration](/fann/setup.html#Runtime%20Configuration)
    -   [Resource Types](/fann/setup.html#Resource%20Types)
-   [Predefined Constants](/fann/constants.html)
-   [Examples](/fann/examples.html)
    -   [XOR training](/fann/examples.html#XOR%20training)
-   [Fann Functions](/ref/fann.html)
    -   [fann\_cascadetrain\_on\_data](/ref/fann.html#fann_cascadetrain_on_data)
        — Trains on an entire dataset, for a period of time using the
        Cascade2 training algorithm
    -   [fann\_cascadetrain\_on\_file](/ref/fann.html#fann_cascadetrain_on_file)
        — Trains on an entire dataset read from file, for a period of
        time using the Cascade2 training algorithm
    -   [fann\_clear\_scaling\_params](/ref/fann.html#fann_clear_scaling_params)
        — Clears scaling parameters
    -   [fann\_copy](/ref/fann.html#fann_copy) — Creates a copy of a
        fann structure
    -   [fann\_create\_from\_file](/ref/fann.html#fann_create_from_file)
        — Constructs a backpropagation neural network from a
        configuration file
    -   [fann\_create\_shortcut\_array](/ref/fann.html#fann_create_shortcut_array)
        — Creates a standard backpropagation neural network which is not
        fully connectected and has shortcut connections
    -   [fann\_create\_shortcut](/ref/fann.html#fann_create_shortcut) —
        Creates a standard backpropagation neural network which is not
        fully connectected and has shortcut connections
    -   [fann\_create\_sparse\_array](/ref/fann.html#fann_create_sparse_array)
        — Creates a standard backpropagation neural network, which is
        not fully connected using an array of layer sizes
    -   [fann\_create\_sparse](/ref/fann.html#fann_create_sparse) —
        Creates a standard backpropagation neural network, which is not
        fully connected
    -   [fann\_create\_standard\_array](/ref/fann.html#fann_create_standard_array)
        — Creates a standard fully connected backpropagation neural
        network using an array of layer sizes
    -   [fann\_create\_standard](/ref/fann.html#fann_create_standard) —
        Creates a standard fully connected backpropagation neural
        network
    -   [fann\_create\_train\_from\_callback](/ref/fann.html#fann_create_train_from_callback)
        — Creates the training data struct from a user supplied function
    -   [fann\_create\_train](/ref/fann.html#fann_create_train) —
        Creates an empty training data struct
    -   [fann\_descale\_input](/ref/fann.html#fann_descale_input) —
        Scale data in input vector after get it from ann based on
        previously calculated parameters
    -   [fann\_descale\_output](/ref/fann.html#fann_descale_output) —
        Scale data in output vector after get it from ann based on
        previously calculated parameters
    -   [fann\_descale\_train](/ref/fann.html#fann_descale_train) —
        Descale input and output data based on previously calculated
        parameters
    -   [fann\_destroy\_train](/ref/fann.html#fann_destroy_train) —
        Destructs the training data
    -   [fann\_destroy](/ref/fann.html#fann_destroy) — Destroys the
        entire network and properly freeing all the associated memory
    -   [fann\_duplicate\_train\_data](/ref/fann.html#fann_duplicate_train_data)
        — Returns an exact copy of a fann train data
    -   [fann\_get\_activation\_function](/ref/fann.html#fann_get_activation_function)
        — Returns the activation function
    -   [fann\_get\_activation\_steepness](/ref/fann.html#fann_get_activation_steepness)
        — Returns the activation steepness for supplied neuron and layer
        number
    -   [fann\_get\_bias\_array](/ref/fann.html#fann_get_bias_array) —
        Get the number of bias in each layer in the network
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
    -   [fann\_get\_errno](/ref/fann.html#fann_get_errno) — Returns the
        last error number
    -   [fann\_get\_errstr](/ref/fann.html#fann_get_errstr) — Returns
        the last errstr
    -   [fann\_get\_layer\_array](/ref/fann.html#fann_get_layer_array) —
        Get the number of neurons in each layer in the network
    -   [fann\_get\_learning\_momentum](/ref/fann.html#fann_get_learning_momentum)
        — Returns the learning momentum
    -   [fann\_get\_learning\_rate](/ref/fann.html#fann_get_learning_rate)
        — Returns the learning rate
    -   [fann\_get\_MSE](/ref/fann.html#fann_get_MSE) — Reads the mean
        square error from the network
    -   [fann\_get\_network\_type](/ref/fann.html#fann_get_network_type)
        — Get the type of neural network it was created as
    -   [fann\_get\_num\_input](/ref/fann.html#fann_get_num_input) — Get
        the number of input neurons
    -   [fann\_get\_num\_layers](/ref/fann.html#fann_get_num_layers) —
        Get the number of layers in the neural network
    -   [fann\_get\_num\_output](/ref/fann.html#fann_get_num_output) —
        Get the number of output neurons
    -   [fann\_get\_quickprop\_decay](/ref/fann.html#fann_get_quickprop_decay)
        — Returns the decay which is a factor that weights should
        decrease in each iteration during quickprop training
    -   [fann\_get\_quickprop\_mu](/ref/fann.html#fann_get_quickprop_mu)
        — Returns the mu factor
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
    -   [fann\_get\_total\_neurons](/ref/fann.html#fann_get_total_neurons)
        — Get the total number of neurons in the entire network
    -   [fann\_get\_train\_error\_function](/ref/fann.html#fann_get_train_error_function)
        — Returns the error function used during training
    -   [fann\_get\_train\_stop\_function](/ref/fann.html#fann_get_train_stop_function)
        — Returns the stop function used during training
    -   [fann\_get\_training\_algorithm](/ref/fann.html#fann_get_training_algorithm)
        — Returns the training algorithm
    -   [fann\_init\_weights](/ref/fann.html#fann_init_weights) —
        Initialize the weights using Widrow + Nguyen’s algorithm
    -   [fann\_length\_train\_data](/ref/fann.html#fann_length_train_data)
        — Returns the number of training patterns in the train data
    -   [fann\_merge\_train\_data](/ref/fann.html#fann_merge_train_data)
        — Merges the train data
    -   [fann\_num\_input\_train\_data](/ref/fann.html#fann_num_input_train_data)
        — Returns the number of inputs in each of the training patterns
        in the train data
    -   [fann\_num\_output\_train\_data](/ref/fann.html#fann_num_output_train_data)
        — Returns the number of outputs in each of the training patterns
        in the train data
    -   [fann\_print\_error](/ref/fann.html#fann_print_error) — Prints
        the error string
    -   [fann\_randomize\_weights](/ref/fann.html#fann_randomize_weights)
        — Give each connection a random weight between min\_weight and
        max\_weight
    -   [fann\_read\_train\_from\_file](/ref/fann.html#fann_read_train_from_file)
        — Reads a file that stores training data
    -   [fann\_reset\_errno](/ref/fann.html#fann_reset_errno) — Resets
        the last error number
    -   [fann\_reset\_errstr](/ref/fann.html#fann_reset_errstr) — Resets
        the last error string
    -   [fann\_reset\_MSE](/ref/fann.html#fann_reset_MSE) — Resets the
        mean square error from the network
    -   [fann\_run](/ref/fann.html#fann_run) — Will run input through
        the neural network
    -   [fann\_save\_train](/ref/fann.html#fann_save_train) — Save the
        training structure to a file
    -   [fann\_save](/ref/fann.html#fann_save) — Saves the entire
        network to a configuration file
    -   [fann\_scale\_input\_train\_data](/ref/fann.html#fann_scale_input_train_data)
        — Scales the inputs in the training data to the specified range
    -   [fann\_scale\_input](/ref/fann.html#fann_scale_input) — Scale
        data in input vector before feed it to ann based on previously
        calculated parameters
    -   [fann\_scale\_output\_train\_data](/ref/fann.html#fann_scale_output_train_data)
        — Scales the outputs in the training data to the specified range
    -   [fann\_scale\_output](/ref/fann.html#fann_scale_output) — Scale
        data in output vector before feed it to ann based on previously
        calculated parameters
    -   [fann\_scale\_train\_data](/ref/fann.html#fann_scale_train_data)
        — Scales the inputs and outputs in the training data to the
        specified range
    -   [fann\_scale\_train](/ref/fann.html#fann_scale_train) — Scale
        input and output data based on previously calculated parameters
    -   [fann\_set\_activation\_function\_hidden](/ref/fann.html#fann_set_activation_function_hidden)
        — Sets the activation function for all of the hidden layers
    -   [fann\_set\_activation\_function\_layer](/ref/fann.html#fann_set_activation_function_layer)
        — Sets the activation function for all the neurons in the
        supplied layer
    -   [fann\_set\_activation\_function\_output](/ref/fann.html#fann_set_activation_function_output)
        — Sets the activation function for the output layer
    -   [fann\_set\_activation\_function](/ref/fann.html#fann_set_activation_function)
        — Sets the activation function for supplied neuron and layer
    -   [fann\_set\_activation\_steepness\_hidden](/ref/fann.html#fann_set_activation_steepness_hidden)
        — Sets the steepness of the activation steepness for all neurons
        in the all hidden layers
    -   [fann\_set\_activation\_steepness\_layer](/ref/fann.html#fann_set_activation_steepness_layer)
        — Sets the activation steepness for all of the neurons in the
        supplied layer number
    -   [fann\_set\_activation\_steepness\_output](/ref/fann.html#fann_set_activation_steepness_output)
        — Sets the steepness of the activation steepness in the output
        layer
    -   [fann\_set\_activation\_steepness](/ref/fann.html#fann_set_activation_steepness)
        — Sets the activation steepness for supplied neuron and layer
        number
    -   [fann\_set\_bit\_fail\_limit](/ref/fann.html#fann_set_bit_fail_limit)
        — Set the bit fail limit used during training
    -   [fann\_set\_callback](/ref/fann.html#fann_set_callback) — Sets
        the callback function for use during training
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
    -   [fann\_set\_error\_log](/ref/fann.html#fann_set_error_log) —
        Sets where the errors are logged to
    -   [fann\_set\_input\_scaling\_params](/ref/fann.html#fann_set_input_scaling_params)
        — Calculate input scaling parameters for future use based on
        training data
    -   [fann\_set\_learning\_momentum](/ref/fann.html#fann_set_learning_momentum)
        — Sets the learning momentum
    -   [fann\_set\_learning\_rate](/ref/fann.html#fann_set_learning_rate)
        — Sets the learning rate
    -   [fann\_set\_output\_scaling\_params](/ref/fann.html#fann_set_output_scaling_params)
        — Calculate output scaling parameters for future use based on
        training data
    -   [fann\_set\_quickprop\_decay](/ref/fann.html#fann_set_quickprop_decay)
        — Sets the quickprop decay factor
    -   [fann\_set\_quickprop\_mu](/ref/fann.html#fann_set_quickprop_mu)
        — Sets the quickprop mu factor
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
        — Calculate input and output scaling parameters for future use
        based on training data
    -   [fann\_set\_train\_error\_function](/ref/fann.html#fann_set_train_error_function)
        — Sets the error function used during training
    -   [fann\_set\_train\_stop\_function](/ref/fann.html#fann_set_train_stop_function)
        — Sets the stop function used during training
    -   [fann\_set\_training\_algorithm](/ref/fann.html#fann_set_training_algorithm)
        — Sets the training algorithm
    -   [fann\_set\_weight\_array](/ref/fann.html#fann_set_weight_array)
        — Set connections in the network
    -   [fann\_set\_weight](/ref/fann.html#fann_set_weight) — Set a
        connection in the network
    -   [fann\_shuffle\_train\_data](/ref/fann.html#fann_shuffle_train_data)
        — Shuffles training data, randomizing the order
    -   [fann\_subset\_train\_data](/ref/fann.html#fann_subset_train_data)
        — Returns an copy of a subset of the train data
    -   [fann\_test\_data](/ref/fann.html#fann_test_data) — Test a set
        of training data and calculates the MSE for the training data
    -   [fann\_test](/ref/fann.html#fann_test) — Test with a set of
        inputs, and a set of desired outputs
    -   [fann\_train\_epoch](/ref/fann.html#fann_train_epoch) — Train
        one epoch with a set of training data
    -   [fann\_train\_on\_data](/ref/fann.html#fann_train_on_data) —
        Trains on an entire dataset for a period of time
    -   [fann\_train\_on\_file](/ref/fann.html#fann_train_on_file) —
        Trains on an entire dataset, which is read from file, for a
        period of time
    -   [fann\_train](/ref/fann.html#fann_train) — Train one iteration
        with a set of inputs, and a set of desired outputs
-   [FANNConnection](/class/fannconnection.html) — The FANNConnection
    class
    -   [FANNConnection::\_\_construct](/class/fannconnection.html#FANNConnection::__construct)
        — The connection constructor
    -   [FANNConnection::getFromNeuron](/class/fannconnection.html#FANNConnection::getFromNeuron)
        — Returns the postions of starting neuron
    -   [FANNConnection::getToNeuron](/class/fannconnection.html#FANNConnection::getToNeuron)
        — Returns the postions of terminating neuron
    -   [FANNConnection::getWeight](/class/fannconnection.html#FANNConnection::getWeight)
        — Returns the connection weight
    -   [FANNConnection::setWeight](/class/fannconnection.html#FANNConnection::setWeight)
        — Sets the connections weight

Introduction
------------

<span class="classname">FANNConnection</span> is used for the neural
network connection. The objects of this class are used in <span
class="function">fann\_get\_connection\_array</span> and <span
class="function">fann\_set\_weight\_array</span>.

Class synopsis
--------------

**FANNConnection**

<span class="ooclass"> class **FANNConnection** </span> {

/\* Properties \*/

<span class="modifier">public</span> `$from_neuron` ;

<span class="modifier">public</span> `$to_neuron` ;

<span class="modifier">public</span> `$weight` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$from_neuron`</span>
, <span class="methodparam"><span class="type">int</span>
`$to_neuron`</span> , <span class="methodparam"><span
class="type">float</span> `$weight`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFromNeuron</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getToNeuron</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getWeight</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setWeight</span> ( <span
class="methodparam"><span class="type">float</span> `$weight`</span> )

}

Properties
----------

`from_neuron`  
The neuron where the connection starts.

`to_neuron`  
The neuron where the connection ends.

`weight`  
The weight of the connection.

FANNConnection::\_\_construct
=============================

The connection constructor

### Description

<span class="modifier">public</span> <span
class="methodname">FANNConnection::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$from_neuron`</span>
, <span class="methodparam"><span class="type">int</span>
`$to_neuron`</span> , <span class="methodparam"><span
class="type">float</span> `$weight`</span> )

Create new connection and initialize its params. After creating the
connection, only weight can be changed.

### Parameters

`from_neuron`  
The postion number of starting neuron.

`to_neuron`  
The postion number of terminating neuron.

`weight`  
The connection weight value.

FANNConnection::getFromNeuron
=============================

Returns the postions of starting neuron

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">FANNConnection::getFromNeuron</span> ( <span
class="methodparam">void</span> )

Returns the postions of starting neuron.

### Parameters

This function has no parameters.

### Return Values

The postions of starting neuron.

FANNConnection::getToNeuron
===========================

Returns the postions of terminating neuron

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">FANNConnection::getToNeuron</span> ( <span
class="methodparam">void</span> )

Returns the postions of terminating neuron.

### Parameters

This function has no parameters.

### Return Values

The postions of terminating neuron.

FANNConnection::getWeight
=========================

Returns the connection weight

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">FANNConnection::getWeight</span> ( <span
class="methodparam">void</span> )

Returns the connection weight.

### Parameters

This function has no parameters.

### Return Values

The connection weight.

FANNConnection::setWeight
=========================

Sets the connections weight

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">FANNConnection::setWeight</span> ( <span
class="methodparam"><span class="type">float</span> `$weight`</span> )

Sets the connection weight.

This method is different than <span
class="function">fann\_set\_weight</span>. It does not update the weight
value in the network. The network value is updated only after calling
<span class="function">fann\_set\_weight\_array</span>.

### Parameters

`weight`  
The connection weight.

### Return Values

No value is returned.

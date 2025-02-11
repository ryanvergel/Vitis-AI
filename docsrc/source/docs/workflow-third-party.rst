========================================
Third-party Inference Stack Integration
========================================

Vitis |trade| AI provides integration support for TVM, ONNX Runtime, and TensorFlow Lite workflows. The developers can leverage these workflows through the subfolders. A brief description of these workflows is as follows:

TVM
---

`TVM.ai <https://tvm.apache.org/>`__ is an Apache Software Foundation project and inference stack that can parse machine learning models from almost any training framework. The model is converted to an intermediate representation (TVM relay), and the stack can then compile the model for various targets, including embedded SoCs, CPUs, GPUs, and x86 and x64 platforms. TVM incorporates an open-source programmable-logic accelerator, the VTA, created using the Xilinx |reg| HLS compiler. TVM supports partitioning a graph into several sub-graphs. These sub-graphs can be targeted to specific accelerators within the target platform (CPU, GPU, VTA, and so on) to enable heterogeneous acceleration.

The VTA is not used for the published Vitis AI - TVM workflow, instead opting to integrate the DPU for offloading compiled subgraphs. Subgraphs that can be partitioned for execution on the DPU are quantized and compiled by the Vitis AI compiler for a specific DPU target. In contrast, the TVM compiler compiles the remaining subgraphs and operations for execution on LLVM.

For additional details of Vitis AI - TVM integration, refer `here <https://tvm.apache.org/docs/how_to/deploy/vitis_ai.html>`__.

.. figure:: reference/images/VAI_3rd_party_TVM.PNG
   :width: 1300

   Vitis-AI Integration With TVM.ai

ONNX Runtime
------------

`ONNX Runtime <https://onnxruntime.ai/>`__ was devised as a cross-platform inference deployment runtime for ONNX models. ONNX Runtime
provides the benefit of runtime interpretation of models represented as an ONNX intermediate representation (IR).

The `ONNX Runtime Execution Provider <https://onnxruntime.ai/docs/execution-providers/>`__ framework enables the integration of proprietary or customized tensor accelerator cores from any “execution provider.” Such “execution providers” are typically tensor acceleration IP blocks integrated into an SoC by the semiconductor vendor. Specific subgraphs or operations within the ONNX graph can be offloaded to that core based on the advertised capabilities of that execution provider. The ability of a given accelerator to offload operations is presented as a listing of capabilities to the ONNX Runtime.

Additional details of the Vitis AI Execution Provider can be found `here <https://onnxruntime.ai/docs/execution-providers/community-maintained/Vitis-AI-ExecutionProvider.html>`__.

As of Vitis AI 3.0, we have enhanced our support for ONNX Runtime in order to on Xilinx targets.  In this context, the Vitis AI Quantizer can be leveraged to export a quantized ONNX model to the runtime where it is compiled.  Users should refer to the section "Programming with VOE" in :doc:`UG1414 <../docs/reference/release_documentation>` for additional information on this new workflow.

.. figure:: reference/images/VAI_3rd_party_ONNXRuntime_Edge.PNG
   :width: 1300
   
   Vitis-AI Integration With ONNX Runtime (Edge)
   
.. figure:: reference/images/VAI_3rd_party_ONNXRuntime.PNG
   :width: 1300

   Vitis-AI Integration With ONNX Runtime (Data Center)


For Xilinx Data Center targets, Vitis AI Execution Provider support has also been published as a `workflow reference <https://github.com/Xilinx/Vitis-AI/tree/v3.0/third_party/onnxruntime>`__ in recent releases.
   


TensorFlow Lite
----------------

TensorFlow Lite has been a preferred inference solution for TensorFlow users in the embedded space for many years. TensorFlow Lite provides support for embedded Arm |reg| processors, as well as NEON tensor acceleration. TensorFlow Lite provides the benefit of runtime interpretation of models trained in TensorFlow Lite, implying that no compilation is required to execute the model on target. This has made TensorFlow Lite a convenient solution for embedded and mobile MCU targets which did not incorporate purpose-built tensor acceleration cores.

With the addition of `TensorFlow Delegates <https://www.tensorflow.org/lite/performance/delegates>`__, it became possible for semiconductor vendors with purpose-built tensor accelerators to integrate support into the TensorFlow Lite framework. Certain operations can be offloaded (delegated) to these specialized accelerators, repositioning TensorFlow Lite runtime interpretation as a useful workflow in the high-performance space.

Vitis AI Delegate support is integrated as an `experimental flow <https://github.com/Xilinx/Vitis-AI/tree/v3.0/third_party/tflite>`__ in recent releases.

.. figure:: reference/images/VAI_3rd_party_TFLite.PNG
   :width: 1300

   Vitis-AI Integration With TensorFlow Lite

.. |trade|  unicode:: U+02122 .. TRADEMARK SIGN
   :ltrim:
.. |reg|    unicode:: U+000AE .. REGISTERED TRADEMARK SIGN
   :ltrim:
# Test Coverage Report (ONNX Core Operators)
## Outlines
* [Node Test Coverage](#node-test-coverage)
* [Model Test Coverage](#model-test-coverage)
* [Overall Test Coverage](#overall-test-coverage)
# Node Test Coverage
## Summary
Node tests have covered 86/100 (0.86%) common operators.

Node tests have covered 1/15 (0.07%) experimental operators.

* [Covered Common Operators](#covered-common-operators)
* [No Cover Common Operators](#no-cover-common-operators)
* [Covered Experimental Operators](#covered-experimental-operators)
* [No Cover Experimental Operators](#no-cover-experimental-operators)

## &#x1F49A;Covered Common Operators
### Abs
There are 1 test cases, listed as following:
<details>
<summary>abs</summary>

```python
node = onnx.helper.make_node(
    'Abs',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.abs(x)

expect(node, inputs=[x], outputs=[y],
       name='test_abs')
```

</details>


### Acos
There are 1 test cases, listed as following:
<details>
<summary>acos</summary>

```python
node = onnx.helper.make_node(
    'Acos',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-0.5, 0, 0.5]).astype(np.float32)
y = np.arccos(x)
expect(node, inputs=[x], outputs=[y],
       name='test_acos_example')

x = np.random.rand(3, 4, 5).astype(np.float32)
y = np.arccos(x)
expect(node, inputs=[x], outputs=[y],
       name='test_acos')
```

</details>


### Add
There are 2 test cases, listed as following:
<details>
<summary>add</summary>

```python
node = onnx.helper.make_node(
    'Add',
    inputs=['x', 'y'],
    outputs=['sum'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(3, 4, 5).astype(np.float32)
expect(node, inputs=[x, y], outputs=[x + y],
       name='test_add')
```

</details>
<details>
<summary>add_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Add',
    inputs=['x', 'y'],
    outputs=['sum'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(5).astype(np.float32)
expect(node, inputs=[x, y], outputs=[x + y],
       name='test_add_bcast')
```

</details>


### And
There are 2 test cases, listed as following:
<details>
<summary>and</summary>

```python
node = onnx.helper.make_node(
    'And',
    inputs=['x', 'y'],
    outputs=['and'],
)

# 2d
x = (np.random.randn(3, 4) > 0).astype(np.bool)
y = (np.random.randn(3, 4) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and2d')

# 3d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and3d')

# 4d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and4d')
```

</details>
<details>
<summary>and_broadcast</summary>

```python
node = onnx.helper.make_node(
    'And',
    inputs=['x', 'y'],
    outputs=['and'],
)

# 3d vs 1d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(5) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and_bcast3v1d')

# 3d vs 2d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(4, 5) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and_bcast3v2d')

# 4d vs 2d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(5, 6) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and_bcast4v2d')

# 4d vs 3d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(4, 5, 6) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and_bcast4v3d')

# 4d vs 4d
x = (np.random.randn(1, 4, 1, 6) > 0).astype(np.bool)
y = (np.random.randn(3, 1, 5, 6) > 0).astype(np.bool)
z = np.logical_and(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_and_bcast4v4d')
```

</details>


### Asin
There are 1 test cases, listed as following:
<details>
<summary>asin</summary>

```python
node = onnx.helper.make_node(
    'Asin',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-0.5, 0, 0.5]).astype(np.float32)
y = np.arcsin(x)
expect(node, inputs=[x], outputs=[y],
       name='test_asin_example')

x = np.random.rand(3, 4, 5).astype(np.float32)
y = np.arcsin(x)
expect(node, inputs=[x], outputs=[y],
       name='test_asin')
```

</details>


### Atan
There are 1 test cases, listed as following:
<details>
<summary>atan</summary>

```python
node = onnx.helper.make_node(
    'Atan',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.arctan(x)
expect(node, inputs=[x], outputs=[y],
       name='test_atan_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.arctan(x)
expect(node, inputs=[x], outputs=[y],
       name='test_atan')
```

</details>


### AveragePool
There are 10 test cases, listed as following:
<details>
<summary>averagepool_1d_default</summary>

```python
"""
iutput_shape: [1, 3, 32]
output_shape: [1, 3, 31]
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2],
)
x = np.random.randn(1, 3, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = [2]
strides = [1]
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, [0], 'AVG')

expect(node, inputs=[x], outputs=[y], name='test_averagepool_1d_default')
```

</details>
<details>
<summary>averagepool_2d_default</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 31, 31]
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (2, 2)
strides = (1, 1)
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, (0, 0), 'AVG')

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_default')
```

</details>
<details>
<summary>averagepool_2d_pads</summary>

```python
"""
iutput_shape: [1, 3, 28, 28]
output_shape: [1, 3, 30, 30]
pad_shape: [4, 4] -> [2, 2, 2, 2] by axis
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[3, 3],
    pads=[2, 2, 2, 2]
)
x = np.random.randn(1, 3, 28, 28).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (3, 3)
strides = (1, 1)
pad_bottom = 2
pad_top = 2
pad_right = 2
pad_left = 2
pad_shape = [pad_top + pad_bottom, pad_left + pad_right]
out_shape = get_output_shape('VALID', np.add(x_shape[2:], pad_shape), kernel_shape, strides)
padded = np.pad(x, ((0, 0), (0, 0), (pad_top, pad_bottom), (pad_left, pad_right)), mode='constant',
                constant_values=np.nan)
y = pool(padded, x_shape, kernel_shape, strides, out_shape, pad_shape, 'AVG')

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_pads')
```

</details>
<details>
<summary>averagepool_2d_precomputed_pads</summary>

```python
"""
input_shape: [1, 1, 5, 5]
output_shape: [1, 1, 5, 5]
pad_shape: [4, 4] -> [2, 2, 2, 2] by axis
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[5, 5],
    pads=[2, 2, 2, 2]

)
x = np.array([[[
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10],
    [11, 12, 13, 14, 15],
    [16, 17, 18, 19, 20],
    [21, 22, 23, 24, 25],
]]]).astype(np.float32)
y = np.array([[[[7, 7.5, 8, 8.5, 9],
                [9.5, 10, 10.5, 11, 11.5],
                [12, 12.5, 13, 13.5, 14],
                [14.5, 15, 15.5, 16, 16.5],
                [17, 17.5, 18, 18.5, 19]]]]).astype(np.float32)

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_precomputed_pads')
```

</details>
<details>
<summary>averagepool_2d_precomputed_same_upper</summary>

```python
"""
input_shape: [1, 1, 5, 5]
output_shape: [1, 1, 3, 3]
pad_shape: [2, 2] -> [1, 1, 1, 1] by axis
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[3, 3],
    strides=[2, 2],
    auto_pad='SAME_UPPER'
)
x = np.array([[[
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10],
    [11, 12, 13, 14, 15],
    [16, 17, 18, 19, 20],
    [21, 22, 23, 24, 25],
]]]).astype(np.float32)
y = np.array([[[[4, 5.5, 7],
                [11.5, 13, 14.5],
                [19, 20.5, 22]]]]).astype(np.float32)

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_precomputed_same_upper')
```

</details>
<details>
<summary>averagepool_2d_precomputed_strides</summary>

```python
"""
input_shape: [1, 1, 5, 5]
output_shape: [1, 1, 2, 2]
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
    strides=[2, 2]
)
x = np.array([[[
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10],
    [11, 12, 13, 14, 15],
    [16, 17, 18, 19, 20],
    [21, 22, 23, 24, 25],
]]]).astype(np.float32)
y = np.array([[[[4, 6],
                [14, 16]]]]).astype(np.float32)

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_precomputed_strides')
```

</details>
<details>
<summary>averagepool_2d_same_lower</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 32, 32]
pad_shape: [1, 1] -> [1, 0, 1, 0] by axis
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
    auto_pad='SAME_LOWER'
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (2, 2)
strides = (1, 1)
out_shape = get_output_shape('SAME_LOWER', x_shape[2:], kernel_shape, strides)
pad_shape = get_pad_shape('SAME_LOWER', x_shape[2:], kernel_shape, strides, out_shape)
pad_bottom = pad_shape[0] // 2
pad_top = pad_shape[0] - pad_bottom
pad_right = pad_shape[1] // 2
pad_left = pad_shape[1] - pad_right
padded = np.pad(x, ((0, 0), (0, 0), (pad_top, pad_bottom), (pad_left, pad_right)), mode='constant',
                constant_values=np.nan)
y = pool(padded, x_shape, kernel_shape, strides, out_shape, pad_shape, 'AVG')

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_same_lower')
```

</details>
<details>
<summary>averagepool_2d_same_upper</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 32, 32]
pad_shape: [1, 1] -> [0, 1, 0, 1] by axis
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
    auto_pad='SAME_UPPER'
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (2, 2)
strides = (1, 1)
out_shape = get_output_shape('SAME_UPPER', x_shape[2:], kernel_shape, strides)
pad_shape = get_pad_shape('SAME_UPPER', x_shape[2:], kernel_shape, strides, out_shape)
pad_top = pad_shape[0] // 2
pad_bottom = pad_shape[0] - pad_top
pad_left = pad_shape[1] // 2
pad_right = pad_shape[1] - pad_left
padded = np.pad(x, ((0, 0), (0, 0), (pad_top, pad_bottom), (pad_left, pad_right)), mode='constant',
                constant_values=np.nan)
y = pool(padded, x_shape, kernel_shape, strides, out_shape, pad_shape, 'AVG')

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_same_upper')
```

</details>
<details>
<summary>averagepool_2d_strides</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 10, 10]
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[5, 5],
    strides=[3, 3]
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (5, 5)
strides = (3, 3)
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, (0, 0), 'AVG')

expect(node, inputs=[x], outputs=[y], name='test_averagepool_2d_strides')
```

</details>
<details>
<summary>averagepool_3d_default</summary>

```python
"""
iutput_shape: [1, 3, 32, 32, 32]
output_shape: [1, 3, 31, 31, 31]
"""
node = onnx.helper.make_node(
    'AveragePool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2, 2],
)
x = np.random.randn(1, 3, 32, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = [2, 2, 2]
strides = [1, 1, 1]
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, [0, 0, 0], 'AVG')

expect(node, inputs=[x], outputs=[y], name='test_averagepool_3d_default')
```

</details>


### Cast
There are 1 test cases, listed as following:
<details>
<summary>cast</summary>

```python
shape = (3, 4)
test_cases = [
    ('FLOAT', 'FLOAT16'),
    ('FLOAT', 'DOUBLE'),
    ('FLOAT16', 'FLOAT'),
    ('FLOAT16', 'DOUBLE'),
    ('DOUBLE', 'FLOAT'),
    ('DOUBLE', 'FLOAT16'),
]

for from_type, to_type in test_cases:
    input = np.random.random_sample(shape).astype(
        TENSOR_TYPE_TO_NP_TYPE[getattr(TensorProto, from_type)])
    node = onnx.helper.make_node(
        'Cast',
        inputs=['input'],
        outputs=['output'],
        to=getattr(TensorProto, to_type),
    )
    output = input.astype(TENSOR_TYPE_TO_NP_TYPE[getattr(TensorProto, to_type)])

    expect(node, inputs=[input], outputs=[output],
           name='test_cast_' + from_type + '_to_' + to_type)
```

</details>


### Ceil
There are 1 test cases, listed as following:
<details>
<summary>ceil</summary>

```python
node = onnx.helper.make_node(
    'Ceil',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1.5, 1.2]).astype(np.float32)
y = np.ceil(x)  # expected output [-1., 2.]
expect(node, inputs=[x], outputs=[y],
       name='test_ceil_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.ceil(x)
expect(node, inputs=[x], outputs=[y],
       name='test_ceil')
```

</details>


### Clip
There are 2 test cases, listed as following:
<details>
<summary>clip</summary>

```python
node = onnx.helper.make_node(
    'Clip',
    inputs=['x'],
    outputs=['y'],
    min=-1.0,
    max=1.0
)

x = np.array([-2, 0, 2]).astype(np.float32)
y = np.clip(x, -1, 1)  # expected output [-1., 0., 1.]
expect(node, inputs=[x], outputs=[y],
       name='test_clip_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, -1.0, 1.0)
expect(node, inputs=[x], outputs=[y],
       name='test_clip')
```

</details>
<details>
<summary>clip_default</summary>

```python
node = onnx.helper.make_node(
    'Clip',
    inputs=['x'],
    outputs=['y'],
    min=0.0
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0.0, np.inf)
expect(node, inputs=[x], outputs=[y],
       name='test_clip_default_min')

node = onnx.helper.make_node(
    'Clip',
    inputs=['x'],
    outputs=['y'],
    max=0.0
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, -np.inf, 0.0)
expect(node, inputs=[x], outputs=[y],
       name='test_clip_default_max')
```

</details>


### Concat
There are 1 test cases, listed as following:
<details>
<summary>concat</summary>

```python
test_cases = {
    '1d': ([1, 2],
           [3, 4]),
    '2d': ([[1, 2], [3, 4]],
           [[5, 6], [7, 8]]),
    '3d': ([[[1, 2], [3, 4]], [[5, 6], [7, 8]]],
           [[[9, 10], [11, 12]], [[13, 14], [15, 16]]])
}  # type: Dict[Text, Sequence[Any]]

for test_case, values_ in test_cases.items():
    values = [np.asarray(v, dtype=np.float32) for v in values_]
    for i in range(len(values[0].shape)):
        in_args = ['value' + str(k) for k in range(len(values))]
        node = onnx.helper.make_node(
            'Concat',
            inputs=[s for s in in_args],
            outputs=['output'],
            axis=i
        )
        output = np.concatenate(values, i)
        expect(node, inputs=[v for v in values], outputs=[output],
               name='test_concat_' + test_case + '_axis_' + str(i))
```

</details>


### Constant
There are 1 test cases, listed as following:
<details>
<summary>constant</summary>

```python
values = np.random.randn(5, 5).astype(np.float32)
node = onnx.helper.make_node(
    'Constant',
    inputs=[],
    outputs=['values'],
    value=onnx.helper.make_tensor(
        name='const_tensor',
        data_type=onnx.TensorProto.FLOAT,
        dims=values.shape,
        vals=values.flatten().astype(float),
    ),
)

expect(node, inputs=[], outputs=[values],
       name='test_constant')
```

</details>


### Conv
There are 2 test cases, listed as following:
<details>
<summary>conv</summary>

```python

x = np.array([[[[0., 1., 2., 3., 4.],  # (1, 1, 5, 5) input tensor
                [5., 6., 7., 8., 9.],
                [10., 11., 12., 13., 14.],
                [15., 16., 17., 18., 19.],
                [20., 21., 22., 23., 24.]]]]).astype(np.float32)
W = np.array([[[[1., 1., 1.],  # (1, 1, 3, 3) tensor for convolution weights
                [1., 1., 1.],
                [1., 1., 1.]]]]).astype(np.float32)

# Convolution with padding
node_with_padding = onnx.helper.make_node(
    'Conv',
    inputs=['x', 'W'],
    outputs=['y'],
    kernel_shape=[3, 3],
    # Default values for other attributes: strides=[1, 1], dilations=[1, 1], groups=1
    pads=[1, 1, 1, 1],
)
y_with_padding = np.array([[[[12., 21., 27., 33., 24.],  # (1, 1, 5, 5) output tensor
                             [33., 54., 63., 72., 51.],
                             [63., 99., 108., 117., 81.],
                             [93., 144., 153., 162., 111.],
                             [72., 111., 117., 123., 84.]]]]).astype(np.float32)
expect(node_with_padding, inputs=[x, W], outputs=[y_with_padding],
       name='test_basic_conv_with_padding')

# Convolution without padding
node_without_padding = onnx.helper.make_node(
    'Conv',
    inputs=['x', 'W'],
    outputs=['y'],
    kernel_shape=[3, 3],
    # Default values for other attributes: strides=[1, 1], dilations=[1, 1], groups=1
    pads=[0, 0, 0, 0],
)
y_without_padding = np.array([[[[54., 63., 72.],  # (1, 1, 3, 3) output tensor
                                [99., 108., 117.],
                                [144., 153., 162.]]]]).astype(np.float32)
expect(node_without_padding, inputs=[x, W], outputs=[y_without_padding],
       name='test_basic_conv_without_padding')
```

</details>
<details>
<summary>conv_with_strides</summary>

```python

x = np.array([[[[0., 1., 2., 3., 4.],  # (1, 1, 7, 5) input tensor
                [5., 6., 7., 8., 9.],
                [10., 11., 12., 13., 14.],
                [15., 16., 17., 18., 19.],
                [20., 21., 22., 23., 24.],
                [25., 26., 27., 28., 29.],
                [30., 31., 32., 33., 34.]]]]).astype(np.float32)
W = np.array([[[[1., 1., 1.],  # (1, 1, 3, 3) tensor for convolution weights
                [1., 1., 1.],
                [1., 1., 1.]]]]).astype(np.float32)

# Convolution with strides=2 and padding
node_with_padding = onnx.helper.make_node(
    'Conv',
    inputs=['x', 'W'],
    outputs=['y'],
    kernel_shape=[3, 3],
    pads=[1, 1, 1, 1],
    strides=[2, 2],  # Default values for other attributes: dilations=[1, 1], groups=1
)
y_with_padding = np.array([[[[12., 27., 24.],  # (1, 1, 4, 3) output tensor
                             [63., 108., 81.],
                             [123., 198., 141.],
                             [112., 177., 124.]]]]).astype(np.float32)
expect(node_with_padding, inputs=[x, W], outputs=[y_with_padding],
       name='test_conv_with_strides_padding')

# Convolution with strides=2 and no padding
node_without_padding = onnx.helper.make_node(
    'Conv',
    inputs=['x', 'W'],
    outputs=['y'],
    kernel_shape=[3, 3],
    pads=[0, 0, 0, 0],
    strides=[2, 2],  # Default values for other attributes: dilations=[1, 1], groups=1
)
y_without_padding = np.array([[[[54., 72.],  # (1, 1, 3, 2) output tensor
                                [144., 162.],
                                [234., 252.]]]]).astype(np.float32)
expect(node_without_padding, inputs=[x, W], outputs=[y_without_padding],
       name='test_conv_with_strides_no_padding')

# Convolution with strides=2 and padding only along one dimension (the H dimension in NxCxHxW tensor)
node_with_asymmetric_padding = onnx.helper.make_node(
    'Conv',
    inputs=['x', 'W'],
    outputs=['y'],
    kernel_shape=[3, 3],
    pads=[1, 0, 1, 0],
    strides=[2, 2],  # Default values for other attributes: dilations=[1, 1], groups=1
)
y_with_asymmetric_padding = np.array([[[[21., 33.],  # (1, 1, 4, 2) output tensor
                                        [99., 117.],
                                        [189., 207.],
                                        [171., 183.]]]]).astype(np.float32)
expect(node_with_asymmetric_padding, inputs=[x, W], outputs=[y_with_asymmetric_padding],
       name='test_conv_with_strides_and_asymmetric_padding')
```

</details>


### ConvTranspose
There are 6 test cases, listed as following:
<details>
<summary>convtranspose</summary>

```python
x = np.array([[[[0., 1., 2.],  # (1, 1, 3, 3)
                [3., 4., 5.],
                [6., 7., 8.]]]]).astype(np.float32)

W = np.array([[[[1., 1., 1.],  # (1, 2, 3, 3)
                [1., 1., 1.],
                [1., 1., 1.]],
               [[1., 1., 1.],
                [1., 1., 1.],
                [1., 1., 1.]]]]).astype(np.float32)

node = onnx.helper.make_node("ConvTranspose", ["X", "W"], ["Y"])

y = np.array([[[[0., 1., 3., 3., 2.],  # (1, 2, 5, 5)
                [3., 8., 15., 12., 7.],
                [9., 21., 36., 27., 15.],
                [9., 20., 33., 24., 13.],
                [6., 13., 21., 15., 8.]],

               [[0., 1., 3., 3., 2.],
                [3., 8., 15., 12., 7.],
                [9., 21., 36., 27., 15.],
                [9., 20., 33., 24., 13.],
                [6., 13., 21., 15., 8.]]]]).astype(np.float32)

expect(node, inputs=[x, W], outputs=[y], name='test_convtranspose')
```

</details>
<details>
<summary>convtranspose_1d</summary>

```python
x = np.array([[[0., 1., 2.]]]).astype(np.float32)  # (1, 1, 3)

W = np.array([[[1., 1., 1.],  # (1, 2, 3)
               [1., 1., 1.]]]).astype(np.float32)

node = onnx.helper.make_node("ConvTranspose", ["X", "W"], ["Y"])

y = np.array([[[0., 1., 3., 3., 2.],  # (1, 2, 5)
               [0., 1., 3., 3., 2.]]]).astype(np.float32)

expect(node, inputs=[x, W], outputs=[y], name='test_convtranspose_1d')
```

</details>
<details>
<summary>convtranspose_3d</summary>

```python
x = np.array([[[[[0., 1., 2., 3., 4.],  # (1, 1, 3, 4, 5)
                 [5., 6., 7., 8., 9.],
                 [10., 11., 12., 13., 14.],
                 [15., 16., 17., 18., 19.]],
                [[20., 21., 22., 23., 24.],
                 [25., 26., 27., 28., 29.],
                 [30., 31., 32., 33., 34.],
                 [35., 36., 37., 38., 39.]],
                [[40., 41., 42., 43., 44.],
                 [45., 46., 47., 48., 49.],
                 [50., 51., 52., 53., 54.],
                 [55., 56., 57., 58., 59.]]]]]).astype(np.float32)

W = np.array([[[[[1., 1., 1.],  # (1, 2, 3, 3, 3)
                 [1., 1., 1.],
                 [1., 1., 1.]],
                [[1., 1., 1.],
                 [1., 1., 1.],
                 [1., 1., 1.]],
                [[1., 1., 1.],
                 [1., 1., 1.],
                 [1., 1., 1.]]],
               [[[1., 1., 1.],
                 [1., 1., 1.],
                 [1., 1., 1.]],
                [[1., 1., 1.],
                 [1., 1., 1.],
                 [1., 1., 1.]],
                [[1., 1., 1.],
                 [1., 1., 1.],
                 [1., 1., 1.]]]]]).astype(np.float32)

node = onnx.helper.make_node("ConvTranspose", ["X", "W"], ["Y"])

y = np.array([[[[[0., 1., 3., 6., 9., 7., 4.],  # (1, 2, 5, 6, 7)
                 [5., 12., 21., 27., 33., 24., 13.],
                 [15., 33., 54., 63., 72., 51., 27.],
                 [30., 63., 99., 108., 117., 81., 42.],
                 [25., 52., 81., 87., 93., 64., 33.],
                 [15., 31., 48., 51., 54., 37., 19.]],

                [[20., 42., 66., 72., 78., 54., 28.],
                 [50., 104., 162., 174., 186., 128., 66.],
                 [90., 186., 288., 306., 324., 222., 114.],
                 [120., 246., 378., 396., 414., 282., 144.],
                 [90., 184., 282., 294., 306., 208., 106.],
                 [50., 102., 156., 162., 168., 114., 58.]],

                [[60., 123., 189., 198., 207., 141., 72.],
                 [135., 276., 423., 441., 459., 312., 159.],
                 [225., 459., 702., 729., 756., 513., 261.],
                 [270., 549., 837., 864., 891., 603., 306.],
                 [195., 396., 603., 621., 639., 432., 219.],
                 [105., 213., 324., 333., 342., 231., 117.]],

                [[60., 122., 186., 192., 198., 134., 68.],
                 [130., 264., 402., 414., 426., 288., 146.],
                 [210., 426., 648., 666., 684., 462., 234.],
                 [240., 486., 738., 756., 774., 522., 264.],
                 [170., 344., 522., 534., 546., 368., 186.],
                 [90., 182., 276., 282., 288., 194., 98.]],

                [[40., 81., 123., 126., 129., 87., 44.],
                 [85., 172., 261., 267., 273., 184., 93.],
                 [135., 273., 414., 423., 432., 291., 147.],
                 [150., 303., 459., 468., 477., 321., 162.],
                 [105., 212., 321., 327., 333., 224., 113.],
                 [55., 111., 168., 171., 174., 117., 59.]]],

               [[[0., 1., 3., 6., 9., 7., 4.],
                 [5., 12., 21., 27., 33., 24., 13.],
                 [15., 33., 54., 63., 72., 51., 27.],
                 [30., 63., 99., 108., 117., 81., 42.],
                 [25., 52., 81., 87., 93., 64., 33.],
                 [15., 31., 48., 51., 54., 37., 19.]],

                [[20., 42., 66., 72., 78., 54., 28.],
                 [50., 104., 162., 174., 186., 128., 66.],
                 [90., 186., 288., 306., 324., 222., 114.],
                 [120., 246., 378., 396., 414., 282., 144.],
                 [90., 184., 282., 294., 306., 208., 106.],
                 [50., 102., 156., 162., 168., 114., 58.]],

                [[60., 123., 189., 198., 207., 141., 72.],
                 [135., 276., 423., 441., 459., 312., 159.],
                 [225., 459., 702., 729., 756., 513., 261.],
                 [270., 549., 837., 864., 891., 603., 306.],
                 [195., 396., 603., 621., 639., 432., 219.],
                 [105., 213., 324., 333., 342., 231., 117.]],

                [[60., 122., 186., 192., 198., 134., 68.],
                 [130., 264., 402., 414., 426., 288., 146.],
                 [210., 426., 648., 666., 684., 462., 234.],
                 [240., 486., 738., 756., 774., 522., 264.],
                 [170., 344., 522., 534., 546., 368., 186.],
                 [90., 182., 276., 282., 288., 194., 98.]],

                [[40., 81., 123., 126., 129., 87., 44.],
                 [85., 172., 261., 267., 273., 184., 93.],
                 [135., 273., 414., 423., 432., 291., 147.],
                 [150., 303., 459., 468., 477., 321., 162.],
                 [105., 212., 321., 327., 333., 224., 113.],
                 [55., 111., 168., 171., 174., 117., 59.]]]]]).astype(np.float32)

expect(node, inputs=[x, W], outputs=[y], name='test_convtranspose_3d')
```

</details>
<details>
<summary>convtranspose_output_padding</summary>

```python
x = np.array([[[[0., 1., 2.],  # (1, 1, 3, 3)
                [3., 4., 5.],
                [6., 7., 8.]]]]).astype(np.float32)

W = np.array([[[[1., 1., 1.],  # (1, 2, 3, 3)
                [1., 1., 1.],
                [1., 1., 1.]],
               [[1., 1., 1.],
                [1., 1., 1.],
                [1., 1., 1.]]]]).astype(np.float32)

node = onnx.helper.make_node("ConvTranspose", ["X", "W"], ["Y"],
                             strides=[3, 2],
                             output_padding=[1, 1])

y = np.array([[[[0., 0., 1., 1., 3., 2., 2., 0.],  # (1, 2, 10, 8)
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [0., 0., 0., 0., 0., 0., 0., 0.]],

               [[0., 0., 1., 1., 3., 2., 2., 0.],
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [0., 0., 0., 0., 0., 0., 0., 0.]]]]).astype(np.float32)

expect(node, inputs=[x, W], outputs=[y], name='test_convtranspose_pad')
```

</details>
<details>
<summary>convtranspose_output_shape</summary>

```python
x = np.array([[[[0., 1., 2.],  # (1, 1, 3, 3)
                [3., 4., 5.],
                [6., 7., 8.]]]]).astype(np.float32)

W = np.array([[[[1., 1., 1.],  # (1, 2, 3, 3)
                [1., 1., 1.],
                [1., 1., 1.]],
               [[1., 1., 1.],
                [1., 1., 1.],
                [1., 1., 1.]]]]).astype(np.float32)

node = onnx.helper.make_node("ConvTranspose", ["X", "W"], ["Y"],
                             strides=[3, 2],
                             output_shape=[1, 2, 10, 8])

y = np.array([[[[0., 0., 1., 1., 3., 2., 2., 0.],  # (1, 2, 10, 8)
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [0., 0., 0., 0., 0., 0., 0., 0.]],

               [[0., 0., 1., 1., 3., 2., 2., 0.],
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [0., 0., 1., 1., 3., 2., 2., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [3., 3., 7., 4., 9., 5., 5., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [6., 6., 13., 7., 15., 8., 8., 0.],
                [0., 0., 0., 0., 0., 0., 0., 0.]]]]).astype(np.float32)

expect(node, inputs=[x, W], outputs=[y], name='test_convtranspose_output_shape')
```

</details>
<details>
<summary>convtranspose_pads</summary>

```python
x = np.array([[[[0., 1., 2.],  # (1, 1, 3, 3)
                [3., 4., 5.],
                [6., 7., 8.]]]]).astype(np.float32)

W = np.array([[[[1., 1., 1.],  # (1, 2, 3, 3)
                [1., 1., 1.],
                [1., 1., 1.]],
               [[1., 1., 1.],
                [1., 1., 1.],
                [1., 1., 1.]]]]).astype(np.float32)

node = onnx.helper.make_node("ConvTranspose", ["X", "W"], ["Y"],
                             strides=[3, 2],
                             pads=[1, 2, 1, 2])

y = np.array([[[[1., 1., 3.],  # (1, 2, 7, 3)
                [1., 1., 3.],
                [7., 4., 9.],
                [7., 4., 9.],
                [7., 4., 9.],
                [13., 7., 15.],
                [13., 7., 15.]],

               [[1., 1., 3.],
                [1., 1., 3.],
                [7., 4., 9.],
                [7., 4., 9.],
                [7., 4., 9.],
                [13., 7., 15.],
                [13., 7., 15.]]]]).astype(np.float32)

expect(node, inputs=[x, W], outputs=[y], name='test_convtranspose_pads')
```

</details>


### Cos
There are 1 test cases, listed as following:
<details>
<summary>cos</summary>

```python
node = onnx.helper.make_node(
    'Cos',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.cos(x)
expect(node, inputs=[x], outputs=[y],
       name='test_cos_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.cos(x)
expect(node, inputs=[x], outputs=[y],
       name='test_cos')
```

</details>


### DepthToSpace
There are 2 test cases, listed as following:
<details>
<summary>depthtospace</summary>

```python
b, c, h, w = shape = (2, 8, 3, 3)
blocksize = 2
node = onnx.helper.make_node(
    'DepthToSpace',
    inputs=['x'],
    outputs=['y'],
    blocksize=blocksize,
)
x = np.random.random_sample(shape).astype(np.float32)
tmp = np.reshape(x, [b, blocksize, blocksize, c // (blocksize**2), h, w])
tmp = np.transpose(tmp, [0, 3, 4, 1, 5, 2])
y = np.reshape(tmp, [b, c // (blocksize**2), h * blocksize, w * blocksize])
expect(node, inputs=[x], outputs=[y],
       name='test_depthtospace')
```

</details>
<details>
<summary>example</summary>

```python
node = onnx.helper.make_node(
    'DepthToSpace',
    inputs=['x'],
    outputs=['y'],
    blocksize=2,
)

# (1, 4, 2, 3) input tensor
x = np.array([[[[0, 1, 2],
                [3, 4, 5]],
               [[6, 7, 8],
                [9, 10, 11]],
               [[12, 13, 14],
                [15, 16, 17]],
               [[18, 19, 20],
                [21, 22, 23]]]]).astype(np.float32)

# (1, 1, 4, 6) output tensor
y = np.array([[[[0, 6, 1, 7, 2, 8],
                [12, 18, 13, 19, 14, 20],
                [3, 9, 4, 10, 5, 11],
                [15, 21, 16, 22, 17, 23]]]]).astype(np.float32)
expect(node, inputs=[x], outputs=[y],
       name='test_depthtospace_example')
```

</details>


### Div
There are 2 test cases, listed as following:
<details>
<summary>div</summary>

```python
node = onnx.helper.make_node(
    'Div',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.array([3, 4]).astype(np.float32)
y = np.array([1, 2]).astype(np.float32)
z = x / y  # expected output [3., 2.]
expect(node, inputs=[x, y], outputs=[z],
       name='test_div_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.rand(3, 4, 5).astype(np.float32) + 1.0
z = x / y
expect(node, inputs=[x, y], outputs=[z],
       name='test_div')
```

</details>
<details>
<summary>div_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Div',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.rand(5).astype(np.float32) + 1.0
z = x / y
expect(node, inputs=[x, y], outputs=[z],
       name='test_div_bcast')
```

</details>


### Elu
There are 2 test cases, listed as following:
<details>
<summary>elu</summary>

```python
node = onnx.helper.make_node(
    'Elu',
    inputs=['x'],
    outputs=['y'],
    alpha=2.0
)

x = np.array([-1, 0, 1]).astype(np.float32)
# expected output [-1.2642411, 0., 1.]
y = np.clip(x, 0, np.inf) + (np.exp(np.clip(x, -np.inf, 0)) - 1) * 2.0
expect(node, inputs=[x], outputs=[y],
       name='test_elu_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf) + (np.exp(np.clip(x, -np.inf, 0)) - 1) * 2.0
expect(node, inputs=[x], outputs=[y],
       name='test_elu')
```

</details>
<details>
<summary>elu_default</summary>

```python
default_alpha = 1.0
node = onnx.helper.make_node(
    'Elu',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf) + (np.exp(np.clip(x, -np.inf, 0)) - 1) * default_alpha
expect(node, inputs=[x], outputs=[y],
       name='test_elu_default')
```

</details>


### Equal
There are 2 test cases, listed as following:
<details>
<summary>equal</summary>

```python
node = onnx.helper.make_node(
    'Equal',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = (np.random.randn(3, 4, 5) * 10).astype(np.int32)
y = (np.random.randn(3, 4, 5) * 10).astype(np.int32)
z = np.equal(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_equal')
```

</details>
<details>
<summary>equal_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Equal',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = (np.random.randn(3, 4, 5) * 10).astype(np.int32)
y = (np.random.randn(5) * 10).astype(np.int32)
z = np.equal(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_equal_bcast')
```

</details>


### Exp
There are 1 test cases, listed as following:
<details>
<summary>exp</summary>

```python
node = onnx.helper.make_node(
    'Exp',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.exp(x)  # expected output [0.36787945, 1., 2.71828175]
expect(node, inputs=[x], outputs=[y],
       name='test_exp_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.exp(x)
expect(node, inputs=[x], outputs=[y],
       name='test_exp')
```

</details>


### Flatten
There are 2 test cases, listed as following:
<details>
<summary>flatten</summary>

```python
shape = (2, 3, 4, 5)
a = np.random.random_sample(shape).astype(np.float32)

for i in range(len(shape)):
    node = onnx.helper.make_node(
        'Flatten',
        inputs=['a'],
        outputs=['b'],
        axis=i,
    )

    new_shape = (1, -1) if i == 0 else (np.prod(shape[0:i]).astype(int), -1)
    b = np.reshape(a, new_shape)
    expect(node, inputs=[a], outputs=[b],
           name='test_flatten_axis' + str(i))
```

</details>
<details>
<summary>flatten_with_default_axis</summary>

```python
node = onnx.helper.make_node(
    'Flatten',
    inputs=['a'],
    outputs=['b'],  # Default value for axis: axis=1
)

shape = (5, 4, 3, 2)
a = np.random.random_sample(shape).astype(np.float32)
new_shape = (5, 24)
b = np.reshape(a, new_shape)
expect(node, inputs=[a], outputs=[b],
       name='test_flatten_default_axis')
```

</details>


### Floor
There are 1 test cases, listed as following:
<details>
<summary>floor</summary>

```python
node = onnx.helper.make_node(
    'Floor',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1.5, 1.2, 2]).astype(np.float32)
y = np.floor(x)  # expected output [-2., 1., 2.]
expect(node, inputs=[x], outputs=[y],
       name='test_floor_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.floor(x)
expect(node, inputs=[x], outputs=[y],
       name='test_floor')
```

</details>


### GRU
There are 3 test cases, listed as following:
<details>
<summary>defaults</summary>

```python
input = np.array([[[1., 2.], [3., 4.], [5., 6.]]]).astype(np.float32)

input_size = 2
hidden_size = 5
weight_scale = 0.1
number_of_gates = 3

node = onnx.helper.make_node(
    'GRU',
    inputs=['X', 'W', 'R'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = weight_scale * np.ones((1, number_of_gates * hidden_size, input_size)).astype(np.float32)
R = weight_scale * np.ones((1, number_of_gates * hidden_size, hidden_size)).astype(np.float32)

gru = GRU_Helper(X=input, W=W, R=R)
_, Y_h = gru.step()
expect(node, inputs=[input, W, R], outputs=[Y_h.astype(np.float32)], name='test_gru_defaults')
```

</details>
<details>
<summary>initial_bias</summary>

```python
input = np.array([[[1., 2., 3.], [4., 5., 6.], [7., 8., 9.]]]).astype(np.float32)

input_size = 3
hidden_size = 3
weight_scale = 0.1
custom_bias = 0.1
number_of_gates = 3

node = onnx.helper.make_node(
    'GRU',
    inputs=['X', 'W', 'R', 'B'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = weight_scale * np.ones((1, number_of_gates * hidden_size, input_size)).astype(np.float32)
R = weight_scale * np.ones((1, number_of_gates * hidden_size, hidden_size)).astype(np.float32)

# Adding custom bias
W_B = custom_bias * np.ones((1, number_of_gates * hidden_size)).astype(np.float32)
R_B = np.zeros((1, number_of_gates * hidden_size)).astype(np.float32)
B = np.concatenate((W_B, R_B), axis=1)

gru = GRU_Helper(X=input, W=W, R=R, B=B)
_, Y_h = gru.step()
expect(node, inputs=[input, W, R, B], outputs=[Y_h.astype(np.float32)], name='test_gru_with_initial_bias')
```

</details>
<details>
<summary>seq_length</summary>

```python
input = np.array([[[1., 2., 3.], [4., 5., 6.], [7., 8., 9.]],
                  [[10., 11., 12.], [13., 14., 15.], [16., 17., 18.]]]).astype(np.float32)

input_size = 3
hidden_size = 5
number_of_gates = 3

node = onnx.helper.make_node(
    'GRU',
    inputs=['X', 'W', 'R', 'B'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = np.random.randn(1, number_of_gates * hidden_size, input_size).astype(np.float32)
R = np.random.randn(1, number_of_gates * hidden_size, hidden_size).astype(np.float32)

# Adding custom bias
W_B = np.random.randn(1, number_of_gates * hidden_size).astype(np.float32)
R_B = np.random.randn(1, number_of_gates * hidden_size).astype(np.float32)
B = np.concatenate((W_B, R_B), axis=1)

gru = GRU_Helper(X=input, W=W, R=R, B=B)
_, Y_h = gru.step()
expect(node, inputs=[input, W, R, B], outputs=[Y_h.astype(np.float32)], name='test_gru_seq_length')
```

</details>


### Gather
There are 2 test cases, listed as following:
<details>
<summary>gather_0</summary>

```python
node = onnx.helper.make_node(
    'Gather',
    inputs=['data', 'indices'],
    outputs=['y'],
    axis=0,
)
data = np.random.randn(5, 4, 3, 2).astype(np.float32)
indices = np.array([0, 1, 3])
y = np.take(data, indices, axis=0)

expect(node, inputs=[data, indices.astype(np.int64)], outputs=[y],
       name='test_gather_0')
```

</details>
<details>
<summary>gather_1</summary>

```python
node = onnx.helper.make_node(
    'Gather',
    inputs=['data', 'indices'],
    outputs=['y'],
    axis=1,
)
data = np.random.randn(5, 4, 3, 2).astype(np.float32)
indices = np.array([0, 1, 3])
y = np.take(data, indices, axis=1)

expect(node, inputs=[data, indices.astype(np.int64)], outputs=[y],
       name='test_gather_1')
```

</details>


### Gemm
There are 2 test cases, listed as following:
<details>
<summary>notranspose</summary>

```python
node = onnx.helper.make_node(
    'Gemm',
    inputs=['a', 'b', 'c'],
    outputs=['y'],
    alpha=0.5,
    beta=0.5
)
a = np.random.ranf([3, 6]).astype(np.float32)
b = np.random.ranf([6, 4]).astype(np.float32)
c = np.random.ranf([3, 4]).astype(np.float32)
y = 0.5 * np.dot(a, b) + 0.5 * c
expect(node, inputs=[a, b, c], outputs=[y],
       name='test_gemm_nobroadcast')
```

</details>
<details>
<summary>transpose</summary>

```python
node = onnx.helper.make_node(
    'Gemm',
    inputs=['a', 'b', 'c'],
    outputs=['y'],
    alpha=0.5,
    beta=0.5,
    transA=1,
    transB=1
)
a = np.random.ranf([6, 3]).astype(np.float32)
b = np.random.ranf([4, 6]).astype(np.float32)
c = np.random.ranf([1, 1]).astype(np.float32)
y = 0.5 * np.dot(a.T, b.T) + 0.5 * c
expect(node, inputs=[a, b, c], outputs=[y],
       name='test_gemm_broadcast')
```

</details>


### GlobalAveragePool
There are 2 test cases, listed as following:
<details>
<summary>globalaveragepool</summary>

```python
node = onnx.helper.make_node(
    'GlobalAveragePool',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(1, 3, 5, 5).astype(np.float32)
spatial_shape = np.ndim(x) - 2
y = np.average(x, axis=tuple(range(spatial_shape, spatial_shape + 2)))
for _ in range(spatial_shape):
    y = np.expand_dims(y, -1)
expect(node, inputs=[x], outputs=[y], name='test_globalaveragepool')
```

</details>
<details>
<summary>globalaveragepool_precomputed</summary>

```python

node = onnx.helper.make_node(
    'GlobalAveragePool',
    inputs=['x'],
    outputs=['y'],
)
x = np.array([[[
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
]]]).astype(np.float32)
y = np.array([[[[5]]]]).astype(np.float32)
expect(node, inputs=[x], outputs=[y], name='test_globalaveragepool_precomputed')
```

</details>


### GlobalMaxPool
There are 2 test cases, listed as following:
<details>
<summary>globalmaxpool</summary>

```python

node = onnx.helper.make_node(
    'GlobalMaxPool',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(1, 3, 5, 5).astype(np.float32)
spatial_shape = np.ndim(x) - 2
y = np.max(x, axis=tuple(range(spatial_shape, spatial_shape + 2)))
for _ in range(spatial_shape):
    y = np.expand_dims(y, -1)
expect(node, inputs=[x], outputs=[y], name='test_globalmaxpool')
```

</details>
<details>
<summary>globalmaxpool_precomputed</summary>

```python

node = onnx.helper.make_node(
    'GlobalMaxPool',
    inputs=['x'],
    outputs=['y'],
)
x = np.array([[[
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
]]]).astype(np.float32)
y = np.array([[[[9]]]]).astype(np.float32)
expect(node, inputs=[x], outputs=[y], name='test_globalmaxpool_precomputed')
```

</details>


### Greater
There are 2 test cases, listed as following:
<details>
<summary>greater</summary>

```python
node = onnx.helper.make_node(
    'Greater',
    inputs=['x', 'y'],
    outputs=['greater'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(3, 4, 5).astype(np.float32)
z = np.greater(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_greater')
```

</details>
<details>
<summary>greater_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Greater',
    inputs=['x', 'y'],
    outputs=['greater'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(5).astype(np.float32)
z = np.greater(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_greater_bcast')
```

</details>


### HardSigmoid
There are 2 test cases, listed as following:
<details>
<summary>hardsigmoid</summary>

```python
node = onnx.helper.make_node(
    'HardSigmoid',
    inputs=['x'],
    outputs=['y'],
    alpha=0.5,
    beta=0.6
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.clip(x * 0.5 + 0.6, 0, 1)  # expected output [0.1, 0.6, 1.]
expect(node, inputs=[x], outputs=[y],
       name='test_hardsigmoid_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x * 0.5 + 0.6, 0, 1)
expect(node, inputs=[x], outputs=[y],
       name='test_hardsigmoid')
```

</details>
<details>
<summary>hardsigmoid_default</summary>

```python
default_alpha = 0.2
default_beta = 0.5
node = onnx.helper.make_node(
    'HardSigmoid',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x * default_alpha + default_beta, 0, 1)
expect(node, inputs=[x], outputs=[y],
       name='test_hardsigmoid_default')
```

</details>


### Hardmax
There are 2 test cases, listed as following:
<details>
<summary>hardmax</summary>

```python
node = onnx.helper.make_node(
    'Hardmax',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([[3, 0, 1, 2], [2, 5, 1, 0], [0, 1, 3, 2], [0, 1, 2, 3]]).astype(np.float32)
y = np.array([[1, 0, 0, 0], [0, 1, 0, 0], [0, 0, 1, 0], [0, 0, 0, 1]]).astype(np.float32)
expect(node, inputs=[x], outputs=[y],
       name='test_hardmax_example')

# For multiple occurrances of the maximal values, the first occurrence is selected for one-hot output
x = np.array([[3, 3, 3, 1]]).astype(np.float32)
y = np.array([[1, 0, 0, 0]]).astype(np.float32)
expect(node, inputs=[x], outputs=[y],
       name='test_hardmax_one_hot')
```

</details>
<details>
<summary>hardmax_axis</summary>

```python
def hardmax_2d(x):  # type: (np.ndarray) -> np.ndarray
    return np.eye(x.shape[1], dtype=x.dtype)[np.argmax(x, axis=1)]

x = np.random.randn(3, 4, 5).astype(np.float32)
node = onnx.helper.make_node(
    'Hardmax',
    inputs=['x'],
    outputs=['y'],
    axis=0,
)
y = hardmax_2d(x.reshape(1, 60)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_hardmax_axis_0')

node = onnx.helper.make_node(
    'Hardmax',
    inputs=['x'],
    outputs=['y'],
    axis=1,
)
y = hardmax_2d(x.reshape(3, 20)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_hardmax_axis_1')

# default axis is 1
node = onnx.helper.make_node(
    'Hardmax',
    inputs=['x'],
    outputs=['y'],
)
expect(node, inputs=[x], outputs=[y],
       name='test_hardmax_default_axis')

node = onnx.helper.make_node(
    'Hardmax',
    inputs=['x'],
    outputs=['y'],
    axis=2,
)
y = hardmax_2d(x.reshape(12, 5)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_hardmax_axis_2')
```

</details>


### Identity
There are 1 test cases, listed as following:
<details>
<summary>identity</summary>

```python
node = onnx.helper.make_node(
    'Identity',
    inputs=['x'],
    outputs=['y'],
)

data = np.array([[[
    [1, 2],
    [3, 4],
]]], dtype=np.float32)

expect(node, inputs=[data], outputs=[data],
       name='test_identity')
```

</details>


### InstanceNormalization
There are 1 test cases, listed as following:
<details>
<summary>instancenormalization</summary>

```python
def _instancenorm_test_mode(x, s, bias, epsilon=1e-5):  # type: ignore
    dims_x = len(x.shape)
    axis = tuple(range(2, dims_x))
    mean = np.mean(x, axis=axis, keepdims=True)
    var = np.var(x, axis=axis, keepdims=True)
    dim_ones = (1,) * (dims_x - 2)
    s = s.reshape(-1, *dim_ones)
    bias = bias.reshape(-1, *dim_ones)
    return s * (x - mean) / np.sqrt(var + epsilon) + bias

# input size: (1, 2, 1, 3)
x = np.array([[[[-1, 0, 1]], [[2, 3, 4]]]]).astype(np.float32)
s = np.array([1.0, 1.5]).astype(np.float32)
bias = np.array([0, 1]).astype(np.float32)
y = _instancenorm_test_mode(x, s, bias).astype(np.float32)

node = onnx.helper.make_node(
    'InstanceNormalization',
    inputs=['x', 's', 'bias'],
    outputs=['y'],
)

# output size: (1, 2, 1, 3)
expect(node, inputs=[x, s, bias], outputs=[y],
       name='test_instancenorm_example')

# input size: (2, 3, 4, 5)
x = np.random.randn(2, 3, 4, 5).astype(np.float32)
s = np.random.randn(3).astype(np.float32)
bias = np.random.randn(3).astype(np.float32)
epsilon = 1e-2
y = _instancenorm_test_mode(x, s, bias, epsilon).astype(np.float32)

node = onnx.helper.make_node(
    'InstanceNormalization',
    inputs=['x', 's', 'bias'],
    outputs=['y'],
    epsilon=epsilon,
)

# output size: (2, 3, 4, 5)
expect(node, inputs=[x, s, bias], outputs=[y],
       name='test_instancenorm_epsilon')
```

</details>


### LRN
There are 2 test cases, listed as following:
<details>
<summary>default</summary>

```python
alpha = 0.0001
beta = 0.75
bias = 1.0
nsize = 3
node = onnx.helper.make_node(
    'LRN',
    inputs=['x'],
    outputs=['y'],
    size=3
)
x = np.random.randn(5, 5, 5, 5).astype(np.float32)
square_sum = np.zeros((5, 5, 5, 5)).astype(np.float32)
for n, c, h, w in np.ndindex(x.shape):
    square_sum[n, c, h, w] = sum(x[n,
                                   max(0, c - int(math.floor((nsize - 1) / 2))):min(5, c + int(math.ceil((nsize - 1) / 2)) + 1),
                                   h,
                                   w] ** 2)
y = x / ((bias + (alpha / nsize) * square_sum) ** beta)
expect(node, inputs=[x], outputs=[y],
       name='test_lrn_default')
```

</details>
<details>
<summary>lrn</summary>

```python
alpha = 0.0002
beta = 0.5
bias = 2.0
nsize = 3
node = onnx.helper.make_node(
    'LRN',
    inputs=['x'],
    outputs=['y'],
    alpha=alpha,
    beta=beta,
    bias=bias,
    size=nsize
)
x = np.random.randn(5, 5, 5, 5).astype(np.float32)
square_sum = np.zeros((5, 5, 5, 5)).astype(np.float32)
for n, c, h, w in np.ndindex(x.shape):
    square_sum[n, c, h, w] = sum(x[n,
                                   max(0, c - int(math.floor((nsize - 1) / 2))):min(5, c + int(math.ceil((nsize - 1) / 2)) + 1),
                                   h,
                                   w] ** 2)
y = x / ((bias + (alpha / nsize) * square_sum) ** beta)
expect(node, inputs=[x], outputs=[y],
       name='test_lrn')
```

</details>


### LSTM
There are 3 test cases, listed as following:
<details>
<summary>defaults</summary>

```python
input = np.array([[[1., 2.], [3., 4.], [5., 6.]]]).astype(np.float32)

input_size = 2
hidden_size = 3
weight_scale = 0.1
number_of_gates = 4

node = onnx.helper.make_node(
    'LSTM',
    inputs=['X', 'W', 'R'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = weight_scale * np.ones((1, number_of_gates * hidden_size, input_size)).astype(np.float32)
R = weight_scale * np.ones((1, number_of_gates * hidden_size, hidden_size)).astype(np.float32)

lstm = LSTM_Helper(X=input, W=W, R=R)
_, Y_h = lstm.step()
expect(node, inputs=[input, W, R], outputs=[Y_h.astype(np.float32)], name='test_lstm_defaults')
```

</details>
<details>
<summary>initial_bias</summary>

```python
input = np.array([[[1., 2., 3.], [4., 5., 6.], [7., 8., 9.]]]).astype(np.float32)

input_size = 3
hidden_size = 4
weight_scale = 0.1
custom_bias = 0.1
number_of_gates = 4

node = onnx.helper.make_node(
    'LSTM',
    inputs=['X', 'W', 'R', 'B'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = weight_scale * np.ones((1, number_of_gates * hidden_size, input_size)).astype(np.float32)
R = weight_scale * np.ones((1, number_of_gates * hidden_size, hidden_size)).astype(np.float32)

# Adding custom bias
W_B = custom_bias * np.ones((1, number_of_gates * hidden_size)).astype(np.float32)
R_B = np.zeros((1, number_of_gates * hidden_size)).astype(np.float32)
B = np.concatenate((W_B, R_B), 1)

lstm = LSTM_Helper(X=input, W=W, R=R, B=B)
_, Y_h = lstm.step()
expect(node, inputs=[input, W, R, B], outputs=[Y_h.astype(np.float32)], name='test_lstm_with_initial_bias')
```

</details>
<details>
<summary>peepholes</summary>

```python
input = np.array([[[1., 2., 3., 4.], [5., 6., 7., 8.]]]).astype(np.float32)

input_size = 4
hidden_size = 3
weight_scale = 0.1
number_of_gates = 4
number_of_peepholes = 3

node = onnx.helper.make_node(
    'LSTM',
    inputs=['X', 'W', 'R', 'B', 'sequence_lens', 'initial_h', 'initial_c', 'P'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

# Initializing Inputs
W = weight_scale * np.ones((1, number_of_gates * hidden_size, input_size)).astype(np.float32)
R = weight_scale * np.ones((1, number_of_gates * hidden_size, hidden_size)).astype(np.float32)
B = np.zeros((1, 2 * number_of_gates * hidden_size)).astype(np.float32)
seq_lens = np.repeat(input.shape[0], input.shape[1]).astype(np.int32)
init_h = np.zeros((1, input.shape[1], hidden_size)).astype(np.float32)
init_c = np.zeros((1, input.shape[1], hidden_size)).astype(np.float32)
P = weight_scale * np.ones((1, number_of_peepholes * hidden_size)).astype(np.float32)

lstm = LSTM_Helper(X=input, W=W, R=R, B=B, P=P, initial_c=init_c, initial_h=init_h)
_, Y_h = lstm.step()
expect(node, inputs=[input, W, R, B, seq_lens, init_h, init_c, P], outputs=[Y_h.astype(np.float32)],
       name='test_lstm_with_peepholes')
```

</details>


### LeakyRelu
There are 2 test cases, listed as following:
<details>
<summary>leakyrelu</summary>

```python
node = onnx.helper.make_node(
    'LeakyRelu',
    inputs=['x'],
    outputs=['y'],
    alpha=0.1
)

x = np.array([-1, 0, 1]).astype(np.float32)
# expected output [-0.1, 0., 1.]
y = np.clip(x, 0, np.inf) + np.clip(x, -np.inf, 0) * 0.1
expect(node, inputs=[x], outputs=[y],
       name='test_leakyrelu_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf) + np.clip(x, -np.inf, 0) * 0.1
expect(node, inputs=[x], outputs=[y],
       name='test_leakyrelu')
```

</details>
<details>
<summary>leakyrelu_default</summary>

```python
default_alpha = 0.01
node = onnx.helper.make_node(
    'LeakyRelu',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf) + np.clip(x, -np.inf, 0) * default_alpha
expect(node, inputs=[x], outputs=[y],
       name='test_leakyrelu_default')
```

</details>


### Less
There are 2 test cases, listed as following:
<details>
<summary>less</summary>

```python
node = onnx.helper.make_node(
    'Less',
    inputs=['x', 'y'],
    outputs=['less'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(3, 4, 5).astype(np.float32)
z = np.less(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_less')
```

</details>
<details>
<summary>less_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Less',
    inputs=['x', 'y'],
    outputs=['less'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(5).astype(np.float32)
z = np.less(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_less_bcast')
```

</details>


### Log
There are 1 test cases, listed as following:
<details>
<summary>log</summary>

```python
node = onnx.helper.make_node(
    'Log',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([1, 10]).astype(np.float32)
y = np.log(x)  # expected output [0., 2.30258512]
expect(node, inputs=[x], outputs=[y],
       name='test_log_example')

x = np.exp(np.random.randn(3, 4, 5).astype(np.float32))
y = np.log(x)
expect(node, inputs=[x], outputs=[y],
       name='test_log')
```

</details>


### LogSoftmax
There are 2 test cases, listed as following:
<details>
<summary>logsoftmax</summary>

```python
node = onnx.helper.make_node(
    'LogSoftmax',
    inputs=['x'],
    outputs=['y'],
)
x = np.array([[-1, 0, 1]]).astype(np.float32)
# expected output [[-2.40760589, -1.40760589, -0.40760589]]
y = x - np.log(np.sum(np.exp(x), axis=1))
expect(node, inputs=[x], outputs=[y],
       name='test_logsoftmax_example_1')
```

</details>
<details>
<summary>logsoftmax_axis</summary>

```python
def logsoftmax_2d(x):  # type: (np.ndarray) -> np.ndarray
    max_x = np.max(x, axis=1).reshape((-1, 1))
    exp_x = np.exp(x - max_x)
    return x - max_x - np.log(np.sum(exp_x, axis=1).reshape((-1, 1)))

x = np.array([[0, 1, 2, 3], [10000, 10001, 10002, 10003]]).astype(np.float32)
# expected output [[-3.4401896, -2.4401896, -1.44018972, -0.44018969],
#                 [-3.4401896, -2.4401896, -1.44018972, -0.44018969]]
y = logsoftmax_2d(x)

node = onnx.helper.make_node(
    'LogSoftmax',
    inputs=['x'],
    outputs=['y'],
)
expect(node, inputs=[x], outputs=[y],
       name='test_logsoftmax_large_number')

x = np.abs(np.random.randn(3, 4, 5).astype(np.float32))
node = onnx.helper.make_node(
    'LogSoftmax',
    inputs=['x'],
    outputs=['y'],
    axis=0,
)
y = logsoftmax_2d(x.reshape(1, 60)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_logsoftmax_axis_0')

node = onnx.helper.make_node(
    'LogSoftmax',
    inputs=['x'],
    outputs=['y'],
    axis=1,
)
y = logsoftmax_2d(x.reshape(3, 20)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_logsoftmax_axis_1')

# default axis is 1
node = onnx.helper.make_node(
    'LogSoftmax',
    inputs=['x'],
    outputs=['y'],
)
expect(node, inputs=[x], outputs=[y],
       name='test_logsoftmax_default_axis')

node = onnx.helper.make_node(
    'LogSoftmax',
    inputs=['x'],
    outputs=['y'],
    axis=2,
)
y = logsoftmax_2d(x.reshape(12, 5)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_logsoftmax_axis_2')
```

</details>


### MatMul
There are 1 test cases, listed as following:
<details>
<summary>matmul</summary>

```python
node = onnx.helper.make_node(
    'MatMul',
    inputs=['a', 'b'],
    outputs=['c'],
)

# 2d
a = np.random.randn(3, 4).astype(np.float32)
b = np.random.randn(4, 3).astype(np.float32)
c = np.matmul(a, b)
expect(node, inputs=[a, b], outputs=[c],
       name='test_matmul_2d')

# 3d
a = np.random.randn(2, 3, 4).astype(np.float32)
b = np.random.randn(2, 4, 3).astype(np.float32)
c = np.matmul(a, b)
expect(node, inputs=[a, b], outputs=[c],
       name='test_matmul_3d')

# 4d
a = np.random.randn(1, 2, 3, 4).astype(np.float32)
b = np.random.randn(1, 2, 4, 3).astype(np.float32)
c = np.matmul(a, b)
expect(node, inputs=[a, b], outputs=[c],
       name='test_matmul_4d')
```

</details>


### Max
There are 1 test cases, listed as following:
<details>
<summary>max</summary>

```python
data_0 = np.array([3, 2, 1]).astype(np.float32)
data_1 = np.array([1, 4, 4]).astype(np.float32)
data_2 = np.array([2, 5, 3]).astype(np.float32)
result = np.array([3, 5, 4]).astype(np.float32)
node = onnx.helper.make_node(
    'Max',
    inputs=['data_0', 'data_1', 'data_2'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1, data_2], outputs=[result],
       name='test_max_example')

node = onnx.helper.make_node(
    'Max',
    inputs=['data_0'],
    outputs=['result'],
)
expect(node, inputs=[data_0], outputs=[data_0],
       name='test_max_one_input')

result = np.maximum(data_0, data_1)
node = onnx.helper.make_node(
    'Max',
    inputs=['data_0', 'data_1'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1], outputs=[result],
       name='test_max_two_inputs')
```

</details>


### MaxPool
There are 10 test cases, listed as following:
<details>
<summary>maxpool_1d_default</summary>

```python
"""
iutput_shape: [1, 3, 32]
output_shape: [1, 3, 31]
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2],
)
x = np.random.randn(1, 3, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = [2]
strides = [1]
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, [0], 'MAX')

expect(node, inputs=[x], outputs=[y], name='test_maxpool_1d_default')
```

</details>
<details>
<summary>maxpool_2d_default</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 31, 31]
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (2, 2)
strides = (1, 1)
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, (0, 0), 'MAX')

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_default')
```

</details>
<details>
<summary>maxpool_2d_pads</summary>

```python
"""
iutput_shape: [1, 3, 28, 28]
output_shape: [1, 3, 30, 30]
pad_shape: [4, 4] -> [2, 2, 2, 2] by axis
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[3, 3],
    pads=[2, 2, 2, 2]
)
x = np.random.randn(1, 3, 28, 28).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (3, 3)
strides = (1, 1)
pad_bottom = 2
pad_top = 2
pad_right = 2
pad_left = 2
pad_shape = [pad_top + pad_bottom, pad_left + pad_right]
out_shape = get_output_shape('VALID', np.add(x_shape[2:], pad_shape), kernel_shape, strides)
padded = np.pad(x, ((0, 0), (0, 0), (pad_top, pad_bottom), (pad_left, pad_right)), mode='constant',
                constant_values=np.nan)
y = pool(padded, x_shape, kernel_shape, strides, out_shape, pad_shape, 'MAX')

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_pads')
```

</details>
<details>
<summary>maxpool_2d_precomputed_pads</summary>

```python
"""
input_shape: [1, 1, 5, 5]
output_shape: [1, 1, 5, 5]
pad_shape: [4, 4] -> [2, 2, 2, 2] by axis
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[5, 5],
    pads=[2, 2, 2, 2]

)
x = np.array([[[
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10],
    [11, 12, 13, 14, 15],
    [16, 17, 18, 19, 20],
    [21, 22, 23, 24, 25],
]]]).astype(np.float32)
y = np.array([[[
    [13, 14, 15, 15, 15],
    [18, 19, 20, 20, 20],
    [23, 24, 25, 25, 25],
    [23, 24, 25, 25, 25],
    [23, 24, 25, 25, 25]]]]).astype(np.float32)

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_precomputed_pads')
```

</details>
<details>
<summary>maxpool_2d_precomputed_same_upper</summary>

```python
"""
input_shape: [1, 1, 5, 5]
output_shape: [1, 1, 3, 3]
pad_shape: [2, 2] -> [1, 1, 1, 1] by axis
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[3, 3],
    strides=[2, 2],
    auto_pad='SAME_UPPER'
)
x = np.array([[[
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10],
    [11, 12, 13, 14, 15],
    [16, 17, 18, 19, 20],
    [21, 22, 23, 24, 25],
]]]).astype(np.float32)
y = np.array([[[[7, 9, 10],
                [17, 19, 20],
                [22, 24, 25]]]]).astype(np.float32)

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_precomputed_same_upper')
```

</details>
<details>
<summary>maxpool_2d_precomputed_strides</summary>

```python
"""
input_shape: [1, 1, 5, 5]
output_shape: [1, 1, 2, 2]
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
    strides=[2, 2]
)
x = np.array([[[
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10],
    [11, 12, 13, 14, 15],
    [16, 17, 18, 19, 20],
    [21, 22, 23, 24, 25],
]]]).astype(np.float32)
y = np.array([[[[7, 9],
                [17, 19]]]]).astype(np.float32)

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_precomputed_strides')
```

</details>
<details>
<summary>maxpool_2d_same_lower</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 32, 32]
pad_shape: [1, 1] -> [1, 0, 1, 0] by axis
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
    auto_pad='SAME_LOWER'
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (2, 2)
strides = (1, 1)
out_shape = get_output_shape('SAME_LOWER', x_shape[2:], kernel_shape, strides)
pad_shape = get_pad_shape('SAME_LOWER', x_shape[2:], kernel_shape, strides, out_shape)
pad_bottom = pad_shape[0] // 2
pad_top = pad_shape[0] - pad_bottom
pad_right = pad_shape[1] // 2
pad_left = pad_shape[1] - pad_right
padded = np.pad(x, ((0, 0), (0, 0), (pad_top, pad_bottom), (pad_left, pad_right)), mode='constant',
                constant_values=np.nan)
y = pool(padded, x_shape, kernel_shape, strides, out_shape, pad_shape, 'MAX')

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_same_lower')
```

</details>
<details>
<summary>maxpool_2d_same_upper</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 32, 32]
pad_shape: [1, 1] -> [0, 1, 0, 1] by axis
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2],
    auto_pad='SAME_UPPER'
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (2, 2)
strides = (1, 1)
out_shape = get_output_shape('SAME_UPPER', x_shape[2:], kernel_shape, strides)
pad_shape = get_pad_shape('SAME_UPPER', x_shape[2:], kernel_shape, strides, out_shape)
pad_top = pad_shape[0] // 2
pad_bottom = pad_shape[0] - pad_top
pad_left = pad_shape[1] // 2
pad_right = pad_shape[1] - pad_left
padded = np.pad(x, ((0, 0), (0, 0), (pad_top, pad_bottom), (pad_left, pad_right)), mode='constant',
                constant_values=np.nan)
y = pool(padded, x_shape, kernel_shape, strides, out_shape, pad_shape, 'MAX')

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_same_upper')
```

</details>
<details>
<summary>maxpool_2d_strides</summary>

```python
"""
iutput_shape: [1, 3, 32, 32]
output_shape: [1, 3, 10, 10]
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[5, 5],
    strides=[3, 3]
)
x = np.random.randn(1, 3, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = (5, 5)
strides = (3, 3)
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, (0, 0), 'MAX')

expect(node, inputs=[x], outputs=[y], name='test_maxpool_2d_strides')
```

</details>
<details>
<summary>maxpool_3d_default</summary>

```python
"""
iutput_shape: [1, 3, 32, 32, 32]
output_shape: [1, 3, 31, 31, 31]
"""
node = onnx.helper.make_node(
    'MaxPool',
    inputs=['x'],
    outputs=['y'],
    kernel_shape=[2, 2, 2],
)
x = np.random.randn(1, 3, 32, 32, 32).astype(np.float32)
x_shape = np.shape(x)
kernel_shape = [2, 2, 2]
strides = [1, 1, 1]
out_shape = get_output_shape('VALID', x_shape[2:], kernel_shape, strides)
padded = x
y = pool(padded, x_shape, kernel_shape, strides, out_shape, [0, 0, 0], 'MAX')

expect(node, inputs=[x], outputs=[y], name='test_maxpool_3d_default')
```

</details>


### Mean
There are 1 test cases, listed as following:
<details>
<summary>mean</summary>

```python
data_0 = np.array([3, 0, 2]).astype(np.float32)
data_1 = np.array([1, 3, 4]).astype(np.float32)
data_2 = np.array([2, 6, 6]).astype(np.float32)
result = np.array([2, 3, 4]).astype(np.float32)
node = onnx.helper.make_node(
    'Mean',
    inputs=['data_0', 'data_1', 'data_2'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1, data_2], outputs=[result],
       name='test_mean_example')

node = onnx.helper.make_node(
    'Mean',
    inputs=['data_0'],
    outputs=['result'],
)
expect(node, inputs=[data_0], outputs=[data_0],
       name='test_mean_one_input')

result = np.divide(np.add(data_0, data_1), 2.)
node = onnx.helper.make_node(
    'Mean',
    inputs=['data_0', 'data_1'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1], outputs=[result],
       name='test_mean_two_inputs')
```

</details>


### Min
There are 1 test cases, listed as following:
<details>
<summary>min</summary>

```python
data_0 = np.array([3, 2, 1]).astype(np.float32)
data_1 = np.array([1, 4, 4]).astype(np.float32)
data_2 = np.array([2, 5, 0]).astype(np.float32)
result = np.array([1, 2, 0]).astype(np.float32)
node = onnx.helper.make_node(
    'Min',
    inputs=['data_0', 'data_1', 'data_2'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1, data_2], outputs=[result],
       name='test_min_example')

node = onnx.helper.make_node(
    'Min',
    inputs=['data_0'],
    outputs=['result'],
)
expect(node, inputs=[data_0], outputs=[data_0],
       name='test_min_one_input')

result = np.minimum(data_0, data_1)
node = onnx.helper.make_node(
    'Min',
    inputs=['data_0', 'data_1'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1], outputs=[result],
       name='test_min_two_inputs')
```

</details>


### Mul
There are 2 test cases, listed as following:
<details>
<summary>mul</summary>

```python
node = onnx.helper.make_node(
    'Mul',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.array([1, 2, 3]).astype(np.float32)
y = np.array([4, 5, 6]).astype(np.float32)
z = x * y  # expected output [4., 10., 18.]
expect(node, inputs=[x, y], outputs=[z],
       name='test_mul_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(3, 4, 5).astype(np.float32)
z = x * y
expect(node, inputs=[x, y], outputs=[z],
       name='test_mul')
```

</details>
<details>
<summary>mul_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Mul',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(5).astype(np.float32)
z = x * y
expect(node, inputs=[x, y], outputs=[z],
       name='test_mul_bcast')
```

</details>


### Neg
There are 1 test cases, listed as following:
<details>
<summary>neg</summary>

```python
node = onnx.helper.make_node(
    'Neg',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-4, 2]).astype(np.float32)
y = np.negative(x)  # expected output [4., -2.],
expect(node, inputs=[x], outputs=[y],
       name='test_neg_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.negative(x)
expect(node, inputs=[x], outputs=[y],
       name='test_neg')
```

</details>


### Not
There are 1 test cases, listed as following:
<details>
<summary>not</summary>

```python
node = onnx.helper.make_node(
    'Not',
    inputs=['x'],
    outputs=['not'],
)

# 2d
x = (np.random.randn(3, 4) > 0).astype(np.bool)
expect(node, inputs=[x], outputs=[np.logical_not(x)],
       name='test_not_2d')

# 3d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
expect(node, inputs=[x], outputs=[np.logical_not(x)],
       name='test_not_3d')

# 4d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
expect(node, inputs=[x], outputs=[np.logical_not(x)],
       name='test_not_4d')
```

</details>


### Or
There are 2 test cases, listed as following:
<details>
<summary>or</summary>

```python
node = onnx.helper.make_node(
    'Or',
    inputs=['x', 'y'],
    outputs=['or'],
)

# 2d
x = (np.random.randn(3, 4) > 0).astype(np.bool)
y = (np.random.randn(3, 4) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or2d')

# 3d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or3d')

# 4d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or4d')
```

</details>
<details>
<summary>or_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Or',
    inputs=['x', 'y'],
    outputs=['or'],
)

# 3d vs 1d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(5) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or_bcast3v1d')

# 3d vs 2d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(4, 5) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or_bcast3v2d')

# 4d vs 2d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(5, 6) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or_bcast4v2d')

# 4d vs 3d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(4, 5, 6) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or_bcast4v3d')

# 4d vs 4d
x = (np.random.randn(1, 4, 1, 6) > 0).astype(np.bool)
y = (np.random.randn(3, 1, 5, 6) > 0).astype(np.bool)
z = np.logical_or(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_or_bcast4v4d')
```

</details>


### PRelu
There are 2 test cases, listed as following:
<details>
<summary>prelu</summary>

```python
node = onnx.helper.make_node(
    'PRelu',
    inputs=['x', 'slope'],
    outputs=['y'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
slope = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf) + np.clip(x, -np.inf, 0) * slope

expect(node, inputs=[x, slope], outputs=[y],
       name='test_prelu_example')
```

</details>
<details>
<summary>prelu_broadcast</summary>

```python
node = onnx.helper.make_node(
    'PRelu',
    inputs=['x', 'slope'],
    outputs=['y'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
slope = np.random.randn(5).astype(np.float32)
y = np.clip(x, 0, np.inf) + np.clip(x, -np.inf, 0) * slope

expect(node, inputs=[x, slope], outputs=[y],
       name='test_prelu_broadcast')
```

</details>


### Pad
There are 2 test cases, listed as following:
<details>
<summary>constant_pad</summary>

```python
node = onnx.helper.make_node(
    'Pad',
    inputs=['x'],
    outputs=['y'],
    mode='constant',
    value=1.2,
    pads=[0, 0, 1, 3, 0, 0, 2, 4],
)
x = np.random.randn(1, 3, 4, 5).astype(np.float32)
y = np.pad(
    x,
    pad_width=((0, 0), (0, 0), (1, 2), (3, 4)),
    mode='constant',
    constant_values=1.2,
)

expect(node, inputs=[x], outputs=[y],
       name='test_constant_pad')
```

</details>
<details>
<summary>reflection_and_edge_pad</summary>

```python
for mode in ['edge', 'reflect']:
    node = onnx.helper.make_node(
        'Pad',
        inputs=['x'],
        outputs=['y'],
        mode=mode,
        pads=[0, 0, 1, 1, 0, 0, 1, 1]
    )
    x = np.random.randn(1, 3, 4, 5).astype(np.float32)
    y = np.pad(
        x,
        pad_width=((0, 0), (0, 0), (1, 1), (1, 1)),
        mode=mode,
    )

    expect(node, inputs=[x], outputs=[y],
           name='test_{}_pad'.format(mode))
```

</details>


### Pow
There are 2 test cases, listed as following:
<details>
<summary>pow</summary>

```python
node = onnx.helper.make_node(
    'Pow',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.array([1, 2, 3]).astype(np.float32)
y = np.array([4, 5, 6]).astype(np.float32)
z = np.power(x, y)  # expected output [1., 32., 729.]
expect(node, inputs=[x, y], outputs=[z],
       name='test_pow_example')

x = np.arange(60).reshape(3, 4, 5).astype(np.float32)
y = np.random.randn(3, 4, 5).astype(np.float32)
z = np.power(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_pow')
```

</details>
<details>
<summary>pow_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Pow',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.array([1, 2, 3]).astype(np.float32)
y = np.array(2).astype(np.float32)
z = np.power(x, y)  # expected output [1., 4., 9.]
expect(node, inputs=[x, y], outputs=[z],
       name='test_pow_bcast_scalar')

node = onnx.helper.make_node(
    'Pow',
    inputs=['x', 'y'],
    outputs=['z'],
)
x = np.array([[1, 2, 3], [4, 5, 6]]).astype(np.float32)
y = np.array([1, 2, 3]).astype(np.float32)
# expected output [[1, 4, 27], [4, 25, 216]]
z = np.power(x, y).astype(np.float32)
expect(node, inputs=[x, y], outputs=[z],
       name='test_pow_bcast_array')
```

</details>


### RNN
There are 3 test cases, listed as following:
<details>
<summary>defaults</summary>

```python
input = np.array([[[1., 2.], [3., 4.], [5., 6.]]]).astype(np.float32)

input_size = 2
hidden_size = 4
weight_scale = 0.1

node = onnx.helper.make_node(
    'RNN',
    inputs=['X', 'W', 'R'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = weight_scale * np.ones((1, hidden_size, input_size)).astype(np.float32)
R = weight_scale * np.ones((1, hidden_size, hidden_size)).astype(np.float32)

rnn = RNN_Helper(X=input, W=W, R=R)
_, Y_h = rnn.step()
expect(node, inputs=[input, W, R], outputs=[Y_h.astype(np.float32)], name='test_simple_rnn_defaults')
```

</details>
<details>
<summary>initial_bias</summary>

```python
input = np.array([[[1., 2., 3.], [4., 5., 6.], [7., 8., 9.]]]).astype(np.float32)

input_size = 3
hidden_size = 5
custom_bias = 0.1
weight_scale = 0.1

node = onnx.helper.make_node(
    'RNN',
    inputs=['X', 'W', 'R', 'B'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = weight_scale * np.ones((1, hidden_size, input_size)).astype(np.float32)
R = weight_scale * np.ones((1, hidden_size, hidden_size)).astype(np.float32)

# Adding custom bias
W_B = custom_bias * np.ones((1, hidden_size)).astype(np.float32)
R_B = np.zeros((1, hidden_size)).astype(np.float32)
B = np.concatenate((W_B, R_B), axis=1)

rnn = RNN_Helper(X=input, W=W, R=R, B=B)
_, Y_h = rnn.step()
expect(node, inputs=[input, W, R, B], outputs=[Y_h.astype(np.float32)],
       name='test_simple_rnn_with_initial_bias')
```

</details>
<details>
<summary>seq_length</summary>

```python
input = np.array([[[1., 2., 3.], [4., 5., 6.], [7., 8., 9.]],
                  [[10., 11., 12.], [13., 14., 15.], [16., 17., 18.]]]).astype(np.float32)

input_size = 3
hidden_size = 5

node = onnx.helper.make_node(
    'RNN',
    inputs=['X', 'W', 'R', 'B'],
    outputs=['', 'Y'],
    hidden_size=hidden_size
)

W = np.random.randn(1, hidden_size, input_size).astype(np.float32)
R = np.random.randn(1, hidden_size, hidden_size).astype(np.float32)

# Adding custom bias
W_B = np.random.randn(1, hidden_size).astype(np.float32)
R_B = np.random.randn(1, hidden_size).astype(np.float32)
B = np.concatenate((W_B, R_B), axis=1)

rnn = RNN_Helper(X=input, W=W, R=R, B=B)
_, Y_h = rnn.step()
expect(node, inputs=[input, W, R, B], outputs=[Y_h.astype(np.float32)], name='test_rnn_seq_length')
```

</details>


### Reciprocal
There are 1 test cases, listed as following:
<details>
<summary>reciprocal</summary>

```python
node = onnx.helper.make_node(
    'Reciprocal',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-4, 2]).astype(np.float32)
y = np.reciprocal(x)  # expected output [-0.25, 0.5],
expect(node, inputs=[x], outputs=[y],
       name='test_reciprocal_example')

x = np.random.rand(3, 4, 5).astype(np.float32) + 0.5
y = np.reciprocal(x)
expect(node, inputs=[x], outputs=[y],
       name='test_reciprocal')
```

</details>


### ReduceL1
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceL1',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims
)

data = np.reshape(np.arange(1, np.prod(shape) + 1, dtype=np.float32), shape)
#print(data)
#[[[1., 2.], [3., 4.]], [[5., 6.], [7., 8.]], [[9., 10.], [11., 12.]]]

reduced = np.sum(a=np.abs(data), axis=axes, keepdims=keepdims == 1)
#print(reduced)
#[[[78.]]]

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l1_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(a=np.abs(data), axis=axes, keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l1_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [2]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceL1',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims
)

data = np.reshape(np.arange(1, np.prod(shape) + 1, dtype=np.float32), shape)
#print(data)
#[[[1., 2.], [3., 4.]], [[5., 6.], [7., 8.]], [[9., 10.], [11., 12.]]]

reduced = np.sum(a=np.abs(data), axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[3., 7.], [11., 15.], [19., 23.]]

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l1_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(a=np.abs(data), axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l1_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [2]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceL1',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims
)

data = np.reshape(np.arange(1, np.prod(shape) + 1, dtype=np.float32), shape)
#print(data)
#[[[1., 2.], [3., 4.]], [[5., 6.], [7., 8.]], [[9., 10.], [11., 12.]]]

reduced = np.sum(a=np.abs(data), axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[[3.], [7.]], [[11.], [15.]], [[19.], [23.]]]

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l1_keep_dims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(a=np.abs(data), axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l1_keep_dims_random')
```

</details>


### ReduceL2
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceL2',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims
)

data = np.reshape(np.arange(1, np.prod(shape) + 1, dtype=np.float32), shape)
#print(data)
#[[[1., 2.], [3., 4.]], [[5., 6.], [7., 8.]], [[9., 10.], [11., 12.]]]

reduced = np.sqrt(np.sum(
    a=np.square(data), axis=axes, keepdims=keepdims == 1))
#print(reduced)
#[[[25.49509757]]]

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l2_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sqrt(np.sum(
    a=np.square(data), axis=axes, keepdims=keepdims == 1))

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l2_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [2]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceL2',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims
)

data = np.reshape(np.arange(1, np.prod(shape) + 1, dtype=np.float32), shape)
#print(data)
#[[[1., 2.], [3., 4.]], [[5., 6.], [7., 8.]], [[9., 10.], [11., 12.]]]

reduced = np.sqrt(np.sum(
    a=np.square(data), axis=tuple(axes), keepdims=keepdims == 1))
#print(reduced)
#[[2.23606798, 5.],
# [7.81024968, 10.63014581],
# [13.45362405, 16.2788206]]

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l2_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sqrt(np.sum(
    a=np.square(data), axis=tuple(axes), keepdims=keepdims == 1))

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l2_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [2]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceL2',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims
)

data = np.reshape(np.arange(1, np.prod(shape) + 1, dtype=np.float32), shape)
#print(data)
#[[[1., 2.], [3., 4.]], [[5., 6.], [7., 8.]], [[9., 10.], [11., 12.]]]

reduced = np.sqrt(np.sum(
    a=np.square(data), axis=tuple(axes), keepdims=keepdims == 1))
#print(reduced)
#[[[2.23606798], [5.]]
# [[7.81024968], [10.63014581]]
# [[13.45362405], [16.2788206 ]]]

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_l2_keep_dims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sqrt(np.sum(
    a=np.square(data), axis=tuple(axes), keepdims=keepdims == 1))

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_l2_keep_dims_random')
```

</details>


### ReduceLogSum
There are 2 test cases, listed as following:
<details>
<summary>keepdims</summary>

```python
node = onnx.helper.make_node(
    'ReduceLogSum',
    inputs=['data'],
    outputs=["reduced"]
)
data = np.random.ranf([3, 4, 5]).astype(np.float32)
reduced = np.log(np.sum(data, keepdims=True))
expect(node, inputs=[data], outputs=[reduced],
       name='test_reduce_log_sum_default')
```

</details>
<details>
<summary>nokeepdims</summary>

```python
node = onnx.helper.make_node(
    'ReduceLogSum',
    inputs=['data'],
    outputs=["reduced"],
    axes=[2, 1],
    keepdims=0
)
data = np.random.ranf([3, 4, 5]).astype(np.float32)
reduced = np.log(np.sum(data, axis=(2, 1), keepdims=False))
expect(node, inputs=[data], outputs=[reduced],
       name='test_reduce_log_sum_desc_axes')

node = onnx.helper.make_node(
    'ReduceLogSum',
    inputs=['data'],
    outputs=["reduced"],
    axes=[0, 1],
    keepdims=0
)
data = np.random.ranf([3, 4, 5]).astype(np.float32)
reduced = np.log(np.sum(data, axis=(0, 1), keepdims=False))
expect(node, inputs=[data], outputs=[reduced],
       name='test_reduce_log_sum_asc_axes')
```

</details>


### ReduceLogSumExp
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceLogSumExp',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims
)

data = np.array(
    [[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]],
    dtype=np.float32)
reduced = np.log(np.sum(np.exp(data),
                        axis=axes,
                        keepdims=keepdims == 1))
# print(reduced)
# [[[60.00671387]]]

expect(node, inputs=[data], outputs=[reduced],
      name='test_reduce_log_sum_exp_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.log(np.sum(np.exp(data),
                        axis=axes,
                        keepdims=keepdims == 1))
expect(node, inputs=[data], outputs=[reduced],
      name='test_reduce_log_sum_exp_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 0
node = onnx.helper.make_node(
    'ReduceLogSumExp',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims
)

data = np.array(
    [[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]],
    dtype=np.float32)
reduced = np.log(np.sum(
    np.exp(data), axis=tuple(axes), keepdims=keepdims == 1))
# print(reduced)
#[[20., 2.31326175]
# [40.00004578, 2.31326175]
# [60.00671387, 2.31326175]]

expect(node, inputs=[data], outputs=[reduced],
      name='test_reduce_log_sum_exp_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.log(np.sum(
    np.exp(data), axis=tuple(axes), keepdims=keepdims == 1))

expect(node, inputs=[data], outputs=[reduced],
    name='test_reduce_log_sum_exp_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 1
node = onnx.helper.make_node(
    'ReduceLogSumExp',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims
)

data = np.array(
    [[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]],
    dtype=np.float32)
reduced = np.log(np.sum(np.exp(data),
                        axis=tuple(axes),
                        keepdims=keepdims == 1))
# print(reduced)
# [[[20., 2.31326175]]
# [[40.00004578, 2.31326175]]
# [[60.00671387, 2.31326175]]]

expect(node, inputs=[data], outputs=[reduced],
      name='test_reduce_log_sum_exp_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.log(np.sum(np.exp(data),
                        axis=tuple(axes),
                        keepdims=keepdims == 1))

expect(node, inputs=[data], outputs=[reduced],
      name='test_reduce_log_sum_exp_keepdims_random')
```

</details>


### ReduceMax
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1
node = onnx.helper.make_node(
    'ReduceMax',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.maximum.reduce(data, axis=axes, keepdims=keepdims == 1)
#print(reduced)
[[[60.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_max_default_axes_keepdim_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.maximum.reduce(data, axis=axes, keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_max_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceMax',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.maximum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[20., 2.]
# [40., 2.]
# [60., 2.]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_max_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.maximum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_max_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceMax',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.maximum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[[20., 2.]]
# [[40., 2.]]
# [[60., 2.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_max_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.maximum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_max_keepdims_random')
```

</details>


### ReduceMean
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceMean',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.mean(data, axis=axes, keepdims=keepdims == 1)
#print(reduced)
#[[[18.25]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_mean_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.mean(data, axis=axes, keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_mean_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceMean',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.mean(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[12.5, 1.5]
# [35., 1.5]
# [57.5, 1.5]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_mean_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.mean(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_mean_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceMean',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.mean(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[[12.5, 1.5]]
# [[35., 1.5]]
# [[57.5, 1.5]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_mean_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.mean(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_mean_keepdims_random')
```

</details>


### ReduceMin
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceMin',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.minimum.reduce(data, axis=axes, keepdims=keepdims == 1)
#print(reduced)
#[[[1.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_min_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.minimum.reduce(data, axis=axes, keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_min_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceMin',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.minimum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[5., 1.]
# [30., 1.]
# [55., 1.]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_min_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.minimum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_min_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceMin', inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[5, 1], [20, 2]], [[30, 1], [40, 2]], [[55, 1], [60, 2]]], dtype=np.float32)
reduced = np.minimum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[[5., 1.]]
# [[30., 1.]]
# [[55., 1.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_min_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.minimum.reduce(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_min_keepdims_random')
```

</details>


### ReduceProd
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceProd',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.prod(data, axis=axes, keepdims=keepdims == 1)
#print(reduced)
#[[[4.790016e+08]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_prod_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.prod(data, axis=axes, keepdims=keepdims == 1)
expect(node, inputs=[data], outputs=[reduced], name='test_reduce_prod_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceProd',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.prod(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[3., 8.]
# [35., 48.]
# [99., 120.]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_prod_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.prod(data, axis=tuple(axes), keepdims=keepdims == 1)
expect(node, inputs=[data], outputs=[reduced], name='test_reduce_prod_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceProd',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.prod(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[[3., 8.]]
# [[35., 48.]]
# [[99., 120.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_prod_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.prod(data, axis=tuple(axes), keepdims=keepdims == 1)
expect(node, inputs=[data], outputs=[reduced], name='test_reduce_prod_keepdims_random')
```

</details>


### ReduceSum
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceSum',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.sum(data, axis=axes, keepdims=keepdims == 1)
#print(reduced)
#[[[78.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(data, axis=axes, keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceSum',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.sum(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[4., 6.]
# [12., 14.]
# [20., 22.]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceSum',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.sum(data, axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[[4., 6.]]
# [[12., 14.]]
# [[20., 22.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(data, axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_keepdims_random')
```

</details>


### ReduceSumSquare
There are 3 test cases, listed as following:
<details>
<summary>default_axes_keepdims</summary>

```python
shape = [3, 2, 2]
axes = None
keepdims = 1

node = onnx.helper.make_node(
    'ReduceSumSquare',
    inputs=['data'],
    outputs=['reduced'],
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.sum(np.square(data), axis=axes, keepdims=keepdims == 1)
#print(reduced)
#[[[650.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_square_default_axes_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(np.square(data), axis=axes, keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_square_default_axes_keepdims_random')
```

</details>
<details>
<summary>do_not_keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 0

node = onnx.helper.make_node(
    'ReduceSumSquare',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.sum(np.square(data), axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[10., 20.]
# [74., 100.]
# [202., 244.]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_square_do_not_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(np.square(data), axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_square_do_not_keepdims_random')
```

</details>
<details>
<summary>keepdims</summary>

```python
shape = [3, 2, 2]
axes = [1]
keepdims = 1

node = onnx.helper.make_node(
    'ReduceSumSquare',
    inputs=['data'],
    outputs=['reduced'],
    axes=axes,
    keepdims=keepdims)

data = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]], [[9, 10], [11, 12]]], dtype=np.float32)
reduced = np.sum(np.square(data), axis=tuple(axes), keepdims=keepdims == 1)
#print(reduced)
#[[[10., 20.]]
# [[74., 100.]]
# [[202., 244.]]]

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_square_keepdims_example')

np.random.seed(0)
data = np.random.uniform(-10, 10, shape).astype(np.float32)
reduced = np.sum(np.square(data), axis=tuple(axes), keepdims=keepdims == 1)

expect(node, inputs=[data], outputs=[reduced], name='test_reduce_sum_square_keepdims_random')
```

</details>


### Relu
There are 1 test cases, listed as following:
<details>
<summary>relu</summary>

```python
node = onnx.helper.make_node(
    'Relu',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf)

expect(node, inputs=[x], outputs=[y],
       name='test_relu')
```

</details>


### Reshape
There are 1 test cases, listed as following:
<details>
<summary>reshape</summary>

```python
original_shape = [2, 3, 4]
test_cases = {
    'reordered_dims': np.array([4, 2, 3], dtype=np.int64),
    'reduced_dims': np.array([3, 8], dtype=np.int64),
    'extended_dims': np.array([3, 2, 2, 2], dtype=np.int64),
    'one_dim': np.array([24], dtype=np.int64),
    'negative_dim': np.array([6, -1, 2], dtype=np.int64),
}
data = np.random.random_sample(original_shape).astype(np.float32)

for test_name, shape in test_cases.items():
    node = onnx.helper.make_node(
        'Reshape',
        inputs=['data', 'shape'],
        outputs=['reshaped'],
    )

    reshaped = np.reshape(data, shape)
    expect(node, inputs=[data, shape], outputs=[reshaped],
           name='test_reshape_' + test_name)
```

</details>


### Selu
There are 2 test cases, listed as following:
<details>
<summary>selu</summary>

```python
node = onnx.helper.make_node(
    'Selu',
    inputs=['x'],
    outputs=['y'],
    alpha=2.0,
    gamma=3.0
)

x = np.array([-1, 0, 1]).astype(np.float32)
# expected output [-3.79272318, 0., 3.]
y = np.clip(x, 0, np.inf) * 3.0 + (np.exp(np.clip(x, -np.inf, 0)) - 1) * 2.0 * 3.0
expect(node, inputs=[x], outputs=[y],
       name='test_selu_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf) * 3.0 + (np.exp(np.clip(x, -np.inf, 0)) - 1) * 2.0 * 3.0
expect(node, inputs=[x], outputs=[y],
       name='test_selu')
```

</details>
<details>
<summary>selu_default</summary>

```python
default_alpha = 1.67326319217681884765625
default_gamma = 1.05070102214813232421875
node = onnx.helper.make_node(
    'Selu',
    inputs=['x'],
    outputs=['y'],
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, 0, np.inf) * default_gamma + \
    (np.exp(np.clip(x, -np.inf, 0)) - 1) * default_alpha * default_gamma
expect(node, inputs=[x], outputs=[y],
       name='test_selu_default')
```

</details>


### Shape
There are 1 test cases, listed as following:
<details>
<summary>shape</summary>

```python
node = onnx.helper.make_node(
    'Shape',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([
    [1, 2, 3],
    [4, 5, 6],
]).astype(np.float32)
y = np.array([
    2, 3,
]).astype(np.int64)

expect(node, inputs=[x], outputs=[y],
       name='test_shape_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.array(x.shape).astype(np.int64)

expect(node, inputs=[x], outputs=[y],
       name='test_shape')
```

</details>


### Sigmoid
There are 1 test cases, listed as following:
<details>
<summary>sigmoid</summary>

```python
node = onnx.helper.make_node(
    'Sigmoid',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = 1.0 / (1.0 + np.exp(np.negative(x)))  # expected output [0.26894143, 0.5, 0.7310586]
expect(node, inputs=[x], outputs=[y],
       name='test_sigmoid_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = 1.0 / (1.0 + np.exp(np.negative(x)))
expect(node, inputs=[x], outputs=[y],
       name='test_sigmoid')
```

</details>


### Sin
There are 1 test cases, listed as following:
<details>
<summary>sin</summary>

```python
node = onnx.helper.make_node(
    'Sin',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.sin(x)
expect(node, inputs=[x], outputs=[y],
       name='test_sin_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.sin(x)
expect(node, inputs=[x], outputs=[y],
       name='test_sin')
```

</details>


### Size
There are 1 test cases, listed as following:
<details>
<summary>size</summary>

```python
node = onnx.helper.make_node(
    'Size',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([
    [1, 2, 3],
    [4, 5, 6],
]).astype(np.float32)
y = np.array(6).astype(np.int64)

expect(node, inputs=[x], outputs=[y],
       name='test_size_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.array(x.size).astype(np.int64)

expect(node, inputs=[x], outputs=[y],
       name='test_size')
```

</details>


### Slice
There are 5 test cases, listed as following:
<details>
<summary>slice</summary>

```python
node = onnx.helper.make_node(
    'Slice',
    inputs=['x'],
    outputs=['y'],
    axes=[0, 1],
    starts=[0, 0],
    ends=[3, 10],
)

x = np.random.randn(20, 10, 5).astype(np.float32)
y = x[0:3, 0:10]

expect(node, inputs=[x], outputs=[y],
       name='test_slice')
```

</details>
<details>
<summary>slice_default_axes</summary>

```python
node = onnx.helper.make_node(
    'Slice',
    inputs=['x'],
    outputs=['y'],
    starts=[0, 0, 3],
    ends=[20, 10, 4],
)

x = np.random.randn(20, 10, 5).astype(np.float32)
y = x[:, :, 3:4]

expect(node, inputs=[x], outputs=[y],
       name='test_slice_default_axes')
```

</details>
<details>
<summary>slice_end_out_of_bounds</summary>

```python
node = onnx.helper.make_node(
    'Slice',
    inputs=['x'],
    outputs=['y'],
    axes=[1],
    starts=[1],
    ends=[1000],
)

x = np.random.randn(20, 10, 5).astype(np.float32)
y = x[:, 1:1000]

expect(node, inputs=[x], outputs=[y],
       name='test_slice_end_out_of_bounds')
```

</details>
<details>
<summary>slice_neg</summary>

```python
node = onnx.helper.make_node(
    'Slice',
    inputs=['x'],
    outputs=['y'],
    axes=[1],
    starts=[0],
    ends=[-1],
)

x = np.random.randn(20, 10, 5).astype(np.float32)
y = x[:, 0:-1]

expect(node, inputs=[x], outputs=[y],
       name='test_slice_neg')
```

</details>
<details>
<summary>slice_start_out_of_bounds</summary>

```python
node = onnx.helper.make_node(
    'Slice',
    inputs=['x'],
    outputs=['y'],
    axes=[1],
    starts=[1000],
    ends=[1000],
)

x = np.random.randn(20, 10, 5).astype(np.float32)
y = x[:, 1000:1000]

expect(node, inputs=[x], outputs=[y],
       name='test_slice_start_out_of_bounds')
```

</details>


### Softmax
There are 2 test cases, listed as following:
<details>
<summary>softmax</summary>

```python
node = onnx.helper.make_node(
    'Softmax',
    inputs=['x'],
    outputs=['y'],
)
x = np.array([[-1, 0, 1]]).astype(np.float32)
# expected output [[0.09003058, 0.24472848, 0.66524094]]
y = np.exp(x) / np.sum(np.exp(x), axis=1)
expect(node, inputs=[x], outputs=[y],
       name='test_softmax_example')
```

</details>
<details>
<summary>softmax_axis</summary>

```python
def softmax_2d(x):  # type: (np.ndarray) -> np.ndarray
    max_x = np.max(x, axis=1).reshape((-1, 1))
    exp_x = np.exp(x - max_x)
    return exp_x / np.sum(exp_x, axis=1).reshape((-1, 1))

x = np.array([[0, 1, 2, 3], [10000, 10001, 10002, 10003]]).astype(np.float32)
# expected output [[0.0320586, 0.08714432, 0.23688284, 0.64391428],
#                 [0.0320586, 0.08714432, 0.23688284, 0.64391428]]
y = softmax_2d(x)

node = onnx.helper.make_node(
    'Softmax',
    inputs=['x'],
    outputs=['y'],
)
expect(node, inputs=[x], outputs=[y],
       name='test_softmax_large_number')

x = np.abs(np.random.randn(3, 4, 5).astype(np.float32))
node = onnx.helper.make_node(
    'Softmax',
    inputs=['x'],
    outputs=['y'],
    axis=0,
)
y = softmax_2d(x.reshape(1, 60)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_softmax_axis_0')

node = onnx.helper.make_node(
    'Softmax',
    inputs=['x'],
    outputs=['y'],
    axis=1,
)
y = softmax_2d(x.reshape(3, 20)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_softmax_axis_1')

# default axis is 1
node = onnx.helper.make_node(
    'Softmax',
    inputs=['x'],
    outputs=['y'],
)
expect(node, inputs=[x], outputs=[y],
       name='test_softmax_default_axis')

node = onnx.helper.make_node(
    'Softmax',
    inputs=['x'],
    outputs=['y'],
    axis=2,
)
y = softmax_2d(x.reshape(12, 5)).reshape(3, 4, 5)
expect(node, inputs=[x], outputs=[y],
       name='test_softmax_axis_2')
```

</details>


### Softplus
There are 1 test cases, listed as following:
<details>
<summary>softplus</summary>

```python
node = onnx.helper.make_node(
    'Softplus',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.log(np.exp(x) + 1)  # expected output [0.31326166, 0.69314718, 1.31326163]
expect(node, inputs=[x], outputs=[y],
       name='test_softplus_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.log(np.exp(x) + 1)
expect(node, inputs=[x], outputs=[y],
       name='test_softplus')
```

</details>


### Softsign
There are 1 test cases, listed as following:
<details>
<summary>softsign</summary>

```python
node = onnx.helper.make_node(
    'Softsign',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.array([-0.5, 0, 0.5]).astype(np.float32)
expect(node, inputs=[x], outputs=[y],
       name='test_softsign_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = x / (1 + np.abs(x))
expect(node, inputs=[x], outputs=[y],
       name='test_softsign')
```

</details>


### Split
There are 3 test cases, listed as following:
<details>
<summary>1d</summary>

```python
input = np.array([1., 2., 3., 4., 5., 6.]).astype(np.float32)

node = onnx.helper.make_node(
    'Split',
    inputs=['input'],
    outputs=['output_1', 'output_2', 'output_3'],
    axis=0
)

expected_outputs = [np.array([1., 2.]).astype(np.float32), np.array([3., 4.]).astype(np.float32), np.array([5., 6.]).astype(np.float32)]
expect(node, inputs=[input], outputs=[y for y in expected_outputs], name='test_split_equal_parts_1d')

node = onnx.helper.make_node(
    'Split',
    inputs=['input'],
    outputs=['output_1', 'output_2'],
    axis=0,
    split=[2, 4]
)

expected_outputs = [np.array([1., 2.]).astype(np.float32), np.array([3., 4., 5., 6.]).astype(np.float32)]
expect(node, inputs=[input], outputs=[y for y in expected_outputs], name='test_split_variable_parts_1d')
```

</details>
<details>
<summary>2d</summary>

```python
input = np.array([[1., 2., 3., 4., 5., 6.],
                  [7., 8., 9., 10., 11., 12.]]).astype(np.float32)

node = onnx.helper.make_node(
    'Split',
    inputs=['input'],
    outputs=['output_1', 'output_2'],
    axis=1
)

expected_outputs = [np.array([[1., 2., 3.], [7., 8., 9.]]).astype(np.float32),
                    np.array([[4., 5., 6.], [10., 11., 12.]]).astype(np.float32)]

expect(node, inputs=[input], outputs=[y for y in expected_outputs], name='test_split_equal_parts_2d')

node = onnx.helper.make_node(
    'Split',
    inputs=['input'],
    outputs=['output_1', 'output_2'],
    axis=1,
    split=[2, 4]
)

expected_outputs = [np.array([[1., 2.], [7., 8.]]).astype(np.float32),
                    np.array([[3., 4., 5., 6.], [9., 10., 11., 12.]]).astype(np.float32)]

expect(node, inputs=[input], outputs=[y for y in expected_outputs], name='test_split_variable_parts_2d')
```

</details>
<details>
<summary>default_values</summary>

```python
input = np.array([1., 2., 3., 4., 5., 6.]).astype(np.float32)

# If axis is not specified, split is applied on default axis 0
node = onnx.helper.make_node(
    'Split',
    inputs=['input'],
    outputs=['output_1', 'output_2', 'output_3']
)

expected_outputs = [np.array([1., 2.]).astype(np.float32), np.array([3., 4.]).astype(np.float32), np.array([5., 6.]).astype(np.float32)]
expect(node, inputs=[input], outputs=[y for y in expected_outputs], name='test_split_equal_parts_default_axis')

node = onnx.helper.make_node(
    'Split',
    inputs=['input'],
    outputs=['output_1', 'output_2'],
    split=[2, 4]
)

expected_outputs = [np.array([1., 2.]).astype(np.float32), np.array([3., 4., 5., 6.]).astype(np.float32)]
expect(node, inputs=[input], outputs=[y for y in expected_outputs], name='test_split_variable_parts_default_axis')
```

</details>


### Sqrt
There are 1 test cases, listed as following:
<details>
<summary>sqrt</summary>

```python
node = onnx.helper.make_node(
    'Sqrt',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([1, 4, 9]).astype(np.float32)
y = np.sqrt(x)  # expected output [1., 2., 3.]
expect(node, inputs=[x], outputs=[y],
       name='test_sqrt_example')

x = np.abs(np.random.randn(3, 4, 5).astype(np.float32))
y = np.sqrt(x)
expect(node, inputs=[x], outputs=[y],
       name='test_sqrt')
```

</details>


### Squeeze
There are 1 test cases, listed as following:
<details>
<summary>squeeze</summary>

```python
node = onnx.helper.make_node(
    'Squeeze',
    inputs=['x'],
    outputs=['y'],
    axes=[0],
)
x = np.random.randn(1, 3, 4, 5).astype(np.float32)
y = np.squeeze(x, axis=0)

expect(node, inputs=[x], outputs=[y],
       name='test_squeeze')
```

</details>


### Sub
There are 2 test cases, listed as following:
<details>
<summary>sub</summary>

```python
node = onnx.helper.make_node(
    'Sub',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.array([1, 2, 3]).astype(np.float32)
y = np.array([3, 2, 1]).astype(np.float32)
z = x - y  # expected output [-2., 0., 2.]
expect(node, inputs=[x, y], outputs=[z],
       name='test_sub_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(3, 4, 5).astype(np.float32)
z = x - y
expect(node, inputs=[x, y], outputs=[z],
       name='test_sub')
```

</details>
<details>
<summary>sub_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Sub',
    inputs=['x', 'y'],
    outputs=['z'],
)

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.random.randn(5).astype(np.float32)
z = x - y
expect(node, inputs=[x, y], outputs=[z],
       name='test_sub_bcast')
```

</details>


### Sum
There are 1 test cases, listed as following:
<details>
<summary>sum</summary>

```python
data_0 = np.array([3, 0, 2]).astype(np.float32)
data_1 = np.array([1, 3, 4]).astype(np.float32)
data_2 = np.array([2, 6, 6]).astype(np.float32)
result = np.array([6, 9, 12]).astype(np.float32)
node = onnx.helper.make_node(
    'Sum',
    inputs=['data_0', 'data_1', 'data_2'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1, data_2], outputs=[result],
       name='test_sum_example')

node = onnx.helper.make_node(
    'Sum',
    inputs=['data_0'],
    outputs=['result'],
)
expect(node, inputs=[data_0], outputs=[data_0],
       name='test_sum_one_input')

result = np.add(data_0, data_1)
node = onnx.helper.make_node(
    'Sum',
    inputs=['data_0', 'data_1'],
    outputs=['result'],
)
expect(node, inputs=[data_0, data_1], outputs=[result],
       name='test_sum_two_inputs')
```

</details>


### Tan
There are 1 test cases, listed as following:
<details>
<summary>tan</summary>

```python
node = onnx.helper.make_node(
    'Tan',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.tan(x)
expect(node, inputs=[x], outputs=[y],
       name='test_tan_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.tan(x)
expect(node, inputs=[x], outputs=[y],
       name='test_tan')
```

</details>


### Tanh
There are 1 test cases, listed as following:
<details>
<summary>tanh</summary>

```python
node = onnx.helper.make_node(
    'Tanh',
    inputs=['x'],
    outputs=['y'],
)

x = np.array([-1, 0, 1]).astype(np.float32)
y = np.tanh(x)  # expected output [-0.76159418, 0., 0.76159418]
expect(node, inputs=[x], outputs=[y],
       name='test_tanh_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.tanh(x)
expect(node, inputs=[x], outputs=[y],
       name='test_tanh')
```

</details>


### Tile
There are 2 test cases, listed as following:
<details>
<summary>tile</summary>

```python
node = onnx.helper.make_node(
    'Tile',
    inputs=['x', 'y'],
    outputs=['z']
)

x = np.random.rand(2, 3, 4, 5).astype(np.float32)

repeats = np.random.randint(low=1, high=10, size=(np.ndim(x),)).astype(np.int64)

z = np.tile(x, repeats)

expect(node,
       inputs=[x, repeats],
       outputs=[z],
       name='test_tile')
```

</details>
<details>
<summary>tile_precomputed</summary>

```python
node = onnx.helper.make_node(
    'Tile',
    inputs=['x', 'y'],
    outputs=['z']
)

x = np.array([
    [0, 1],
    [2, 3]
], dtype=np.float32)

repeats = np.array([2, 2], dtype=np.int64)

z = np.array([
    [0, 1, 0, 1],
    [2, 3, 2, 3],
    [0, 1, 0, 1],
    [2, 3, 2, 3]
], dtype=np.float32)

expect(node,
       inputs=[x, repeats],
       outputs=[z],
       name='test_tile_precomputed')
```

</details>


### TopK
There are 1 test cases, listed as following:
<details>
<summary>top_k</summary>

```python
node = onnx.helper.make_node(
    'TopK',
    inputs=['x'],
    outputs=['values', 'indices'],
    k=3
)
X = np.array([
    [0, 1, 2, 3],
    [4, 5, 6, 7],
    [8, 9, 10, 11],
], dtype=np.float32)
values_ref = np.array([
    [3, 2, 1],
    [7, 6, 5],
    [11, 10, 9],
], dtype=np.float32)
indices_ref = np.array([
    [3, 2, 1],
    [3, 2, 1],
    [3, 2, 1],
], dtype=np.int64)

expect(node, inputs=[X], outputs=[values_ref, indices_ref],
       name='test_top_k')
```

</details>


### Transpose
There are 2 test cases, listed as following:
<details>
<summary>all_permutations</summary>

```python
shape = (2, 3, 4)
data = np.random.random_sample(shape).astype(np.float32)
permutations = list(itertools.permutations(np.arange(len(shape))))

for i in range(len(permutations)):
    node = onnx.helper.make_node(
        'Transpose',
        inputs=['data'],
        outputs=['transposed'],
        perm=permutations[i]
    )
    transposed = np.transpose(data, permutations[i])
    expect(node, inputs=[data], outputs=[transposed],
           name='test_transpose_all_permutations_' + str(i))
```

</details>
<details>
<summary>default</summary>

```python
shape = (2, 3, 4)
data = np.random.random_sample(shape).astype(np.float32)

node = onnx.helper.make_node(
    'Transpose',
    inputs=['data'],
    outputs=['transposed']
)

transposed = np.transpose(data)
expect(node, inputs=[data], outputs=[transposed],
       name='test_transpose_default')
```

</details>


### Unsqueeze
There are 1 test cases, listed as following:
<details>
<summary>squeeze</summary>

```python
node = onnx.helper.make_node(
    'Unsqueeze',
    inputs=['x'],
    outputs=['y'],
    axes=[0],
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.expand_dims(x, axis=0)

expect(node, inputs=[x], outputs=[y],
       name='test_unsqueeze')
```

</details>


### Upsample
There are 1 test cases, listed as following:
<details>
<summary>nearest</summary>

```python
node = onnx.helper.make_node(
    'Upsample',
    inputs=['x'],
    outputs=['y'],
    scales=[1.0, 1.0, 2.0, 3.0],
    mode='nearest',
)

data = np.array([[[
    [1, 2],
    [3, 4],
]]], dtype=np.float32)

output = np.array([[[
    [1, 1, 1, 2, 2, 2],
    [1, 1, 1, 2, 2, 2],
    [3, 3, 3, 4, 4, 4],
    [3, 3, 3, 4, 4, 4],
]]], dtype=np.float32)

expect(node, inputs=[data], outputs=[output],
       name='test_upsample_nearest')
```

</details>


### Xor
There are 2 test cases, listed as following:
<details>
<summary>xor</summary>

```python
node = onnx.helper.make_node(
    'Xor',
    inputs=['x', 'y'],
    outputs=['xor'],
)

# 2d
x = (np.random.randn(3, 4) > 0).astype(np.bool)
y = (np.random.randn(3, 4) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor2d')

# 3d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor3d')

# 4d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor4d')
```

</details>
<details>
<summary>xor_broadcast</summary>

```python
node = onnx.helper.make_node(
    'Xor',
    inputs=['x', 'y'],
    outputs=['xor'],
)

# 3d vs 1d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(5) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor_bcast3v1d')

# 3d vs 2d
x = (np.random.randn(3, 4, 5) > 0).astype(np.bool)
y = (np.random.randn(4, 5) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor_bcast3v2d')

# 4d vs 2d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(5, 6) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor_bcast4v2d')

# 4d vs 3d
x = (np.random.randn(3, 4, 5, 6) > 0).astype(np.bool)
y = (np.random.randn(4, 5, 6) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor_bcast4v3d')

# 4d vs 4d
x = (np.random.randn(1, 4, 1, 6) > 0).astype(np.bool)
y = (np.random.randn(3, 1, 5, 6) > 0).astype(np.bool)
z = np.logical_xor(x, y)
expect(node, inputs=[x, y], outputs=[z],
       name='test_xor_bcast4v4d')
```

</details>


<br/>

## &#x1F494;No Cover Common Operators
### ArgMax (call for test cases)


### ArgMin (call for test cases)


### BatchNormalization (call for test cases)


### Dropout (call for test cases)


### GlobalLpPool (call for test cases)


### LpNormalization (call for test cases)


### LpPool (call for test cases)


### MaxRoiPool (call for test cases)


### Multinomial (call for test cases)


### RandomNormal (call for test cases)


### RandomNormalLike (call for test cases)


### RandomUniform (call for test cases)


### RandomUniformLike (call for test cases)


### SpaceToDepth (call for test cases)


<br/>

## &#x1F49A;Covered Experimental Operators
### ThresholdedRelu
There are 2 test cases, listed as following:
<details>
<summary>default</summary>

```python
default_alpha = 1.0
node = onnx.helper.make_node(
    'ThresholdedRelu',
    inputs=['x'],
    outputs=['y']
)
x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, default_alpha, np.inf)
y[y == default_alpha] = 0

expect(node, inputs=[x], outputs=[y],
       name='test_thresholdedrelu_default')
```

</details>
<details>
<summary>thresholdedrelu</summary>

```python
alpha = 2.0
node = onnx.helper.make_node(
    'ThresholdedRelu',
    inputs=['x'],
    outputs=['y'],
    alpha=alpha
)

x = np.array([-1.5, 0., 1.2, 2.0, 2.2]).astype(np.float32)
y = np.clip(x, alpha, np.inf)  # expected output [0., 0., 0., 0., 2.2]
y[y == alpha] = 0

expect(node, inputs=[x], outputs=[y],
       name='test_thresholdedrelu_example')

x = np.random.randn(3, 4, 5).astype(np.float32)
y = np.clip(x, alpha, np.inf)
y[y == alpha] = 0

expect(node, inputs=[x], outputs=[y],
       name='test_thresholdedrelu')
```

</details>


<br/>

## &#x1F494;No Cover Experimental Operators
### ATen (call for test cases)


### Affine (call for test cases)


### ConstantFill (call for test cases)


### Crop (call for test cases)


### GRUUnit (call for test cases)


### GivenTensorFill (call for test cases)


### If (call for test cases)


### ImageScaler (call for test cases)


### Loop (call for test cases)


### LoopIndexTensor (call for test cases)


### MeanVarianceNormalization (call for test cases)


### ParametricSoftplus (call for test cases)


### Scale (call for test cases)


### ScaledTanh (call for test cases)


<br/>

# Model Test Coverage
## To be filled.
# Overall Test Coverage
## To be filled.
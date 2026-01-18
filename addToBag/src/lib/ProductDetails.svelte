<script>
  import img1 from '../assets/polo shirt 1.png';
  import img2 from '../assets/polo shirt 2.png';
  import img3 from '../assets/polo shirt 3.png';

  const product = {
    brand: 'Polo Ralph',
    title: 'Custom Fit Polo Bear Oxford Shirt',
    description: 'Blue polo with a classic cut. Made of smooth and soft cotton',
    discountPrice: 25,
    currency: '$',
    size: {
      S: 499,
      M: 599,
      L: 699,
      XL: 799,
    },
    images: [
      {
        id: 'image1',
        imageUrl: img1,
      },
      {
        id: 'image2',
        imageUrl: img2,
      },
      {
        id: 'image3',
        imageUrl: img3,
      },
    ],
  };
  const defaultImage = $state(0);
</script>

<main>
  <div class="product-images">
    <div class="main-image">
      <img src={product.images[defaultImage].imageUrl} alt="Product Image" />

    </div>
    <div class="thumbnail-images">
      {#each product.images as image, index}
        <img
          src={image.imageUrl}
          alt="Thumbnail Image"
          class:active={index === defaultImage}
        />
      {/each}
    </div>
  </div>
  <div class="product-info">
    <h2 class="product-brand">{product.brand}</h2>
    <h1>{product.title}</h1>
    <p>{product.description}</p>
    <div class="product-pricing">
      <h3></h3>
    </div>
    <h4>Choose Size</h4>
    <div class="size-options">
      {#each Object.entries(product.size) as [size]}
        <button class="size-button">{size}</button>
      {/each}
    </div>
  </div>
</main>

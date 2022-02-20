<template>
  <v-container>
    <h1>Product page</h1>
    <v-form ref="form" class="" lazy-validation> </v-form>
    <v-container class="d-flex align-content-start flex-wrap">
      <v-card
        class="mx-3 mb-5"
        outline
        max-width="250"
        v-for="(prd, index) in productlist"
        :key="index"
      >
        <v-img class="dark--text align-end" height="200px" :src="prd.imageUrl">
        </v-img>

        <v-card-title class="pb-0"> {{ prd.productName }} </v-card-title>
        <v-card-text class="text--primary">
          <h3>Price :฿ {{ prd.price }}</h3>

          <div class="grey--text">{{ prd.detail }}</div>
        </v-card-text>
        <v-card-actions>
          <div class="text-center">
            <v-rating
              v-model="rating"
              color="yellow darken-3"
              background-color="grey darken-1"
              empty-icon="$ratingFull"
              half-increments
              hover
            ></v-rating></div
        ></v-card-actions>
        <v-card-actions>
          <v-btn color="orange" text> {{ prd.ctaText }} </v-btn>

          <v-btn color="info" text :to="'/productdetail/' + prd.productId">
            ดูรายละเอียด
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-container>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      rating: 4.5,
      productlist: [
        {
          productId: "001",
          productName: "Canvas Shoulder Bag",
          price: "999.00",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/cd8323e26bb9bff06692b2c3ef8d72ec5b84fa40_xxl-1.jpg",
          rightText: "Shop All",
          leftText: "LIGHT BEIGE",
          detail:
            "Bag in sturdy cotton canvas with an embroidered appliqué. Two handles and a zipped opening at the top, a detachable, adjustable shoulder strap and one inner compartment. Lined. Depth 10 cm. Height 18 cm. Width 20 cm.",
          headerUrl: "http://www.thenorthface.com/en_US/shop-mens/",
          ctaText: "Shop Now",
        },
        {
          productId: "002",
          productName: "Quilted Shoulder Bag",
          price: "999.00",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/66dd23559fd5e3d7dcb7e4d3a40896eda85c84a5_xxl-1.jpg",
          rightText: "Shop All",
          leftText: "Women's & Men's",
          detail:
            "Lightly padded shoulder bag in a quilted weave with a narrow, adjustable shoulder strap and a flap with a concealed magnetic fastener. One inner compartment. Lined. Depth 8.5 cm. Height 17 cm. Width 25 cm.",
          headerUrl: "http://www.thenorthface.com/en_US/shop-womens/",
          ctaText: "Shop Now",
        },
        {
          productId: "003",
          productName: "Beaded Handbag",
          price: "1,399.0",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/zoom/88b33f8f0725d6639601849a0ba5b510d67e734c_xxl-1.jpg",
          rightText: "Shop All",
          leftText: "Running Shoes",
          detail:
            "Small handbag in shimmering metallic plastic beads. Zip at the top and a handle in plastic beads. Lined. Depth 5 cm. Height without handle 14 cm. Height with handle 36 cm. Width 20 cm.",
          headerUrl:
            "http://www.thenorthface.com/webapp/wcs/stores/servlet/TNFSearchResult?langId=-1&amp;storeId=207&amp;catalogId=10201&amp;searchTerm=running%20shoes",
          ctaText: "Shop Now",
        },
        {
          productId: "004",
          productName: "Shopper",
          price: "1,399.00 ",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/bcf8bbf9d6e4797d4121363163841a76bae32bc3_xxl-1.jpg",
          rightText: "Shop All",
          leftText: "Equipment",
          detail:
            "Imitation leather shopper with two handles at the top and a zipped inner compartment. Depth 14 cm. Height 27 cm. Width 41 cm. Lined.",
          headerUrl: "http://www.thenorthface.com/en_US/shop-equipment/",
          ctaText: "Shop Now",
        },
        {
          productId: "005",
          productName: "Rhinestone-embellished Clutch Bag",
          price: "1,099.00",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/1fde6013004d02f454e275e902905f555d095f6d_xxl-1.jpg",
          rightText: "Shop All",
          detail:
            "COMPOSITIONshell Polyester 100%details Polyester 100%lining Polyester 100%coating Polyurethane 100%",
          ctaText: "Shop Now",
        },
        {
          productId: "006",
          productName: "Jacquard-weave Handbag",
          price: "1,399.00",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/a7bf80c6ea708ffc0cec40600e92f4da8224b8ce_xxl-1.jpg",
          rightText: "Shop All",
          detail:
            "Handbag in a jacquard-weave cotton blend with two handles and a zipped inner compartment. Cotton twill lining. Depth 16 cm. Height 32 cm. Width 41 cm.",
          ctaText: "Shop Now",
        },
        {
          productId: "007",
          productName: "Padded Shoulder-strap Shopper",
          price: "999.00",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/2b2bea14f47e58b306844e9533cc3469a35f6031_xxl-1.jpg",
          rightText: "Shop All",
          detail:
            "Padded shopper in quilted nylon with two handles and a zip at the top and a detachable, adjustable shoulder strap with a metal carabiner hook at each end. Lined. Depth 8 cm. Width 20 cm. Height 21 cm.",
          ctaText: "Shop Now",
        },
        {
          productId: "008",
          productName: "Soft Shopper",
          price: "1,399.00",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/4ebe2204832cc918ab05849ac81d02d49741af9d_xxl-1.jpg",
          rightText: "Shop All",
          detail:
            "Shopper in soft, fluffy fabric with two handles, a concealed magnetic fastener and a zipped inner compartment. Lined. Depth 14.5 cm. Height 32 cm. Width 36.5 cm.",
          ctaText: "Shop Now",
        },
        {
          productId: "009",
          productName: "Mini Backpack",
          price: "1,399.00",
          imageUrl:
            "https://d29c1z66frfv6c.cloudfront.net/pub/media/catalog/product/large/0302e4470b3224abc6d01a6020c91fed42da3dde_xxl-1.jpg",
          rightText: "Shop All",
          detail:
            "Mini backpack in woven fabric with an embroidered appliqué. Handle at the top and adjustable, detachable shoulder straps. Opening with a drawstring at the top and a flap with an adjustable tab that has a metal fastener. Two large outer compartments with a zip and ring pull. Lined. Depth 11 cm. Width 23 cm. Height 27",
          ctaText: "Shop Now",
        },
      ],
    };
  },
};
</script>

<style></style>

<script lang="ts">
      import Icon from "@iconify/svelte";
</script>

<div id="container">
    <nav>
        <a href="/order" class="open"><Icon icon="mdi:cart-outline" inline="true"></Icon></a>
        <a href="/order"><Icon icon="mdi:clipboard-text-clock-outline" inline="true"></Icon></a>
        <a href="/order"><Icon icon="mdi:face-man-profile" inline="true"></Icon></a>
    </nav>

    <main>
        <h1>Bonjour <strong>Timothée</strong>,</h1>
        <div id="categories">
            <div class="card category">
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p>Entrées</p>
            </div>
            <div class="card category">
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p>Entrées</p>
            </div>
            <div class="card category">
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p>Entrées</p>
            </div>
        </div>
        <div id="items">
            <div class="card item">
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="name">Entrées</p>
                <p class="price">5€</p>
            </div>
            <div class="card item">
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="name">Entrées</p>
                <p class="price">5€</p>
            </div>
            <div class="card item">
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="name">Entrées</p>
                <p class="price">5€</p>
            </div>
        </div>
    </main>

    <div id="cart">
        <div class="cart_items">
            <div>
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="price">5.80€</p>
                <p class="amount">x4</p>
            </div>
            <div>
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="price">5.80€</p>
                <p class="amount">x4</p>
            </div>
            <div>
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="price">5.80€</p>
                <p class="amount">x4</p>
            </div>
            <div>
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="price">5.80€</p>
                <p class="amount">x4</p>
            </div>
            <div>
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="price">5.80€</p>
                <p class="amount">x4</p>
            </div>
            <div>
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="price">5.80€</p>
                <p class="amount">x4</p>
            </div>
            <div>
                <img src="https://via.placeholder.com/100" alt="Image de la catégorie">
                <p class="price">5.80€</p>
                <p class="amount">x4</p>
            </div>
        </div>
        <div class="cart_total">
            <p>Total : 0€</p>
            <button>Commander</button>
        </div>
    </div>
</div>

<style lang="scss">
    #container {
        display: block;
        position: relative;
        height: 100vh;
        width: 100vw;
        overflow: hidden;
    }

    h1 {
        margin: 1rem 0;
        font-weight: $font-weight-normal;
        strong {
            font-weight: $font-weight-medium;
        }
    }

    main {
        margin: 1em;
    }

    nav {
        position: absolute;
        z-index: 10;
        bottom: 0;
        height: 4rem;
        width: 100%;
        background-color: #f0f0f0;
        border-top: 2px solid map-get($gray, 200);
        margin: 0;
        padding: 0.25rem;

        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;

        a {
            font-size: 1.5 * $font-size-normal;
            color: map-get($slate, 700);
            padding: 0.25rem 1rem;
        }

        a.open {
            background-color: map-get($primary, 600);
            border-radius: $rounded-full;
            color: $white;
        }
    }

    #categories, #items {
        margin-top: 1rem;
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
        gap: 0.5rem;
    }

    .card {
        border-radius: $rounded-md;
        border: 1px solid map-get($primary, 500);
        align-items: stretch;
        justify-content: center;
        display: flex;
        flex-direction: column;
        text-align: center;
        overflow: hidden;
    }

    .category img, .item img {
        width: 100%;
        aspect-ratio: 1;
        object-fit: cover;
    }

    .category p {
        font-size: $font-size-normal;
        margin: 0.5rem 0.5rem;
        font-weight: $font-weight-semibold;
    }
    
    .item p {
        font-size: $font-size-normal;
        font-weight: $font-weight-normal;

        &.name {
            margin-top: 0.5rem;
            margin-left: 0.5rem;
            margin-right: 0.5rem;
        }

        &.price {
            margin-bottom: 0.5rem;
            margin-left: 0.5rem;
            margin-right: 0.5rem;
            font-weight: $font-weight-semibold;
        }
    }

    #cart {
        position: absolute;
        bottom: 4rem;
        z-index: 5;

        width: calc(100% - 2px - 2rem);
        overflow: hidden;

        border: 1px solid;
        border-color: map-get($gray, 600);
        background-color: $white;
        padding: 1rem 1rem;
        margin: 0;        
        //border-radius: $rounded-xl $rounded-xl 0rem 0rem;

        display: flex;
        flex-direction: column;
        gap: 0.5rem;

        align-items: stretch;
    }

    .cart_items {
        white-space: nowrap;
        overflow-x: scroll;
        margin: 0.5rem 0;
    }

    .cart_items { 
        div {
            display: inline-block;
            position: relative;
            border: 1px solid;
            border-color: map-get($gray, 600);
            border-radius: $rounded-lg;
            overflow: hidden;
            width: 75px;
            height: 75px;
            margin: 0;
            padding: 0;

            img {
                width: 75px;
                aspect-ratio: 1;
                object-fit: cover;
            }

            .price, .amount {
                position: absolute;
                padding: 0.25rem 0.5rem;
                font-size: $font-size-tiny;
                font-weight: $font-weight-semibold;
                color: $white;
                margin: 0;
            }

            .price {
                top: 0;
                left: 0;
                background-color: map-get($primary, 700);
                color: $white;
                border-radius: 0 0 $rounded-lg 0;
            }

            .amount {
                bottom: 0;
                right: 0;
                background-color: map-get($primary, 700);
                border-radius: $rounded-lg 0 0 0;
            }
        }
    }

    .cart_total {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;

        p {
            font-size: $font-size-normal;
            font-weight: $font-weight-semibold;
            margin: 0;
            padding: 0;
        }

        button {
            padding: 0.25rem 1rem;
            font-size: $font-size-normal;
            font-weight: $font-weight-bold;
            background-color: map-get($primary, 600);
            color: $white;
            border-radius: $rounded-lg;
            border: none;
            text-transform: uppercase;

            outline-color: map-get($primary, 200);
        }

        button:hover {
            background-color: map-get($primary, 800);
        }
    }
</style>
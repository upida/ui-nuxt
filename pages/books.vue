<template>
  <div>
    <section id="home" />
    <div class="main-wrap">
      <main-header :data="[]" />
      <main class="container-wrap">
        <parallax-main />
        <section>
            <v-container>
                <v-card>
                    <v-card-title>
                        Books
                        <v-spacer></v-spacer>
                        <v-text-field
                            v-model="search"
                            append-icon="mdi-magnify"
                            label="Search"
                            single-line
                            hide-details
                        ></v-text-field>
                    </v-card-title>
                    <v-data-table
                        :headers="bookHeaders"
                        :items="books"
                        :expanded.sync="expanded"
                        :search="search"
                        item-key="id"
                        show-expand
                        class="elevation-1"
                    >
                        <template v-slot:expanded-item="{ headers, item }">
                            <td :colspan="headers.length">
                                <ul class="my-3">
                                    <li>Publication Date : {{item.publication_date}}</li>
                                    <li>Genre : {{item.genre}}</li>
                                    <li>Price : {{item.price}}</li>
                                    <li>Quantity : {{item.quantity}}</li>
                                </ul>
                            </td>
                        </template>
                    </v-data-table>
                </v-card>
            </v-container>
        </section>
      </main>
      <main-footer />
    </div>
  </div>
</template>

<style scoped lang="scss">
@function section-margin($margin) {
  @return $margin * 15;
}
.main-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
}
.space-bottom {
  margin-bottom: section-margin($spacing1);
}
.space-top {
  padding-top: section-margin($spacing1);
}
.container-wrap {
  margin-top: $spacing15;
  & > section {
    position: relative;
  }
}
</style>

<script>
import Header from '~/components/templates/Header'
import ParallaxMain from '~/components/templates/Parallax/Main'
import Hidden from '~/components/templates/Hidden'
import Footer from '~/components/templates/Footer'
import PageNav from '~/components/templates/PageNav'

export default {
  head() {
    return {
      title: 'Books',
    }
  },
  components: {
    'main-header': Header,
    Hidden,
    ParallaxMain,
    PageNav,
    'main-footer': Footer,
  },
  data() {
    return {
      menu: ['home'],
      search: '',
      expanded: [],
      singleExpand: false,
      bookHeaders: [
        { text: 'ID', value: 'id' },
        { text: 'Title', value: 'title' },
        { text: 'Author', value: 'author' },
        { text: 'Publisher', value: 'publisher' },
        { text: '', value: 'data-table-expand' },
      ],
      books: [
        {
          id: 1,
          title: 'The Alchemist',
          author: 'Paulo Coelho',
          publisher: 'HarperCollins',
          publication_date: '1988-01-01',
          genre: 'Fiction',
          price: 10.99,
          quantity: 100,
        },
        {
          id: 2,
          title: 'The Great Gatsby',
          author: 'F. Scott Fitzgerald',
          publisher: 'Scribner',
          publication_date: '1925-04-10',
          genre: 'Fiction',
          price: 12.99,
          quantity: 75,
        },
        {
          id: 3,
          title: 'To Kill a Mockingbird',
          author: 'Harper Lee',
          publisher: 'J. B. Lippincott & Co.',
          publication_date: '1960-07-11',
          genre: 'Fiction',
          price: 9.99,
          quantity: 50,
        },
        {
          id: 4,
          title: '1984',
          author: 'George Orwell',
          publisher: 'Secker & Warburg',
          publication_date: '1949-06-08',
          genre: 'Fiction',
          price: 11.99,
          quantity: 120,
        },
        {
          id: 5,
          title: 'Animal Farm',
          author: 'George Orwell',
          publisher: 'Secker & Warburg',
          publication_date: '1945-08-17',
          genre: 'Fiction',
          price: 8.99,
          quantity: 90,
        },
        {
          id: 6,
          title: 'The Hobbit',
          author: 'J. R. R. Tolkien',
          publisher: 'George Allen & Unwin',
          publication_date: '1937-09-21',
          genre: 'Fantasy',
          price: 14.99,
          quantity: 70,
        },
        {
          id: 7,
          title: 'The Lord of the Rings',
          author: 'J. R. R. Tolkien',
          publisher: 'George Allen & Unwin',
          publication_date: '1954-07-29',
          genre: 'Fantasy',
          price: 29.99,
          quantity: 40,
        },
        {
          id: 8,
          title: 'The Catcher in the Rye',
          author: 'J. D. Salinger',
          publisher: 'Little, Brown and Company',
          publication_date: '1951-07-16',
          genre: 'Fiction',
          price: 10.99,
          quantity: 80,
        },
        {
          id: 9,
          title: 'Pride and Prejudice',
          author: 'Jane Austen',
          publisher: 'T. Egerton, Whitehall',
          publication_date: '1813-01-28',
          genre: 'Romance',
          price: 7.99,
          quantity: 60,
        },
        {
          id: 10,
          title: 'Jane Eyre',
          author: 'Charlotte Bronte',
          publisher: 'Smith, Elder & Co.',
          publication_date: '1847-10-16',
          genre: 'Gothic Fiction',
          price: 9.99,
          quantity: 50,
        },
        {
          id: 11,
          title: 'The Picture of Dorian Gray',
          author: 'Oscar Wilde',
          publisher: 'Ward, Lock & Co.',
          publication_date: '1890-07-01',
          genre: 'Gothic Fiction',
          price: 11.99,
          quantity: 70,
        },
        {
          id: 12,
          title: 'The Adventures of Tom Sawyer',
          author: 'Mark Twain',
          publisher: 'Chatto & Windus',
          publication_date: '1876-12-01',
          genre: 'Fiction',
          price: 8.99,
          quantity: 90,
        },
        {
          id: 13,
          title: 'The Adventures of Huckleberry Finn',
          author: 'Mark Twain',
          publisher: 'Chatto & Windus',
          publication_date: '1884-12-10',
          genre: 'Fiction',
          price: 10.99,
          quantity: 80,
        },
        {
          id: 14,
          title: 'Moby-Dick; or, The Whale',
          author: 'Herman Melville',
          publisher: 'Richard Bentley',
          publication_date: '1851-10-18',
          genre: 'Fiction',
          price: 12.99,
          quantity: 60,
        },
        {
          id: 15,
          title: 'Don Quixote',
          author: 'Miguel de Cervantes',
          publisher: 'Francisco de Robles',
          publication_date: '1605-01-16',
          genre: 'Satire',
          price: 14.99,
          quantity: 100,
        },
        {
          id: 16,
          title: 'The Odyssey',
          author: 'Homer',
          publisher: 'None',
          publication_date: '8th century BCE',
          genre: 'Epic Poetry',
          price: 9.99,
          quantity: 120,
        },
        {
          id: 17,
          title: 'The Divine Comedy',
          author: 'Dante Alighieri',
          publisher: 'None',
          publication_date: '1320-1321',
          genre: 'Epic Poetry',
          price: 11.99,
          quantity: 70,
        },
        {
          id: 18,
          title: 'War and Peace',
          author: 'Leo Tolstoy',
          publisher: 'The Russian Messenger',
          publication_date: '1869',
          genre: 'Historical Fiction',
          price: 17.99,
          quantity: 40,
        },
        {
          id: 19,
          title: 'The Brothers Karamazov',
          author: 'Fyodor Dostoevsky',
          publisher: 'The Russian Messenger',
          publication_date: '1880',
          genre: 'Philosophical Fiction',
          price: 15.99,
          quantity: 60,
        },
        {
          id: 20,
          title: 'The Great Gatsby',
          author: 'F. Scott Fitzgerald',
          publisher: "Charles Scribner's Sons",
          publication_date: '1925-04-10',
          genre: 'Fiction',
          price: 9.99,
          quantity: 80,
        },
        {
          id: 21,
          title: 'To Kill a Mockingbird',
          author: 'Harper Lee',
          publisher: 'J. B. Lippincott & Co.',
          publication_date: '1960-07-11',
          genre: 'Southern Gothic',
          price: 12.99,
          quantity: 50,
        },
      ],
    }
  },
  watch: {},
  methods: {},
}
</script>

<template>
  <ul class="share-buttons">
    <div class="title is-size-7">{{$t('shareButtonTitle')}}</div>
    <li>
      <a
        :href="facebookLink"
        target="_blank"
        title="Share on Facebook"
      >
        <i class="fab fa-facebook-square fa-2x" aria-hidden="true"></i>
        <span class="sr-only">Share on Facebook</span>
      </a>
    </li>
    <li>
      <a
        :href="twitterLink"
        target="_blank"
        title="Tweet"
      >
        <i class="fab fa-twitter-square fa-2x" aria-hidden="true"></i>
        <span class="sr-only">Tweet</span>
      </a>
    </li>
    <li>
      <a
        :href="pinterestLink"
        target="_blank"
        title="Pin it">
          <i class="fab fa-pinterest-square fa-2x" aria-hidden="true"></i>
          <span class="sr-only">Pin it</span>
      </a>
    </li>
    <li>
      <a
        :href="redditLink"
        target="_blank"
        title="Submit to Reddit"
      >
        <i class="fab fa-reddit-square fa-2x" aria-hidden="true"></i>
        <span class="sr-only">Submit to Reddit</span>
      </a>
    </li>
    <li>
      <a
        :href="mailLink"
        target="_blank"
        title="Send email"
      >
        <i class="fas fa-envelope-square fa-2x" aria-hidden="true"></i>
        <span class="sr-only">Send email</span>
      </a>
    </li>
    <li>
      <a
        :href="pocketLink"
        target="_blank"
        title="Add to Pocket">
          <i class="fab fab fa-get-pocket fa-2x" aria-hidden="true"></i>
          <span class="sr-only">Add to Pocket</span>
      </a>
    </li>
  </ul>
</template>


<script>
const url = 'https://badtranslator.net/';
const imageUrl = 'https://flxn.de/qrcode2stl/img/generate_code.9da711b0.gif';
const twitterhandle = 'flxnde';

export default {
  name: 'Header',
  props: {
    title: {
        type: String,
        default: 'Play the BadTranslator game',
    },
    text: {
        type: String,
        default: 'On BadTranslator.net you can play the "Telephone Game" with online translators. Translate your text through random languages and see what comes out.',
    },
  },
  data() {
    return {
        mailLink: `mailto:?subject=${encodeURIComponent(this.title)}&body=${encodeURIComponent(`${this.text}: ${url}`)}`,
        facebookLink: `https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(url)}&quote=${encodeURIComponent(`${this.text}: ${url}`)}`,
        twitterLink: `https://twitter.com/intent/tweet?source=${encodeURIComponent(url)}&text=${encodeURIComponent(`${this.text}: ${url}`)}&via=${twitterhandle}`,
        redditLink: `http://www.reddit.com/submit?url=${encodeURIComponent(url)}&title=${encodeURIComponent(this.text)}`,
        pinterestLink: `http://pinterest.com/pin/create/button/?url=${encodeURIComponent(url)}&media=${encodeURIComponent(imageUrl)}&description=${encodeURIComponent(this.text)}`,
        pocketLink: `https://getpocket.com/save?url=${encodeURIComponent(url)}&title=${encodeURIComponent(this.title)}`,
    };
  },
};
</script>

<style scoped>
ul.share-buttons {
  list-style: none;
  padding: 0;
}

ul.share-buttons li {
  display: inline;
  margin: 0 5px;
}

ul.share-buttons .title {
  margin-bottom: 2px;
  margin-left: 5px;
}

ul.share-buttons li a {
  color: #363636;
}

ul.share-buttons li a:hover {
  color: #4a4a4a;
}

ul.share-buttons .sr-only {
  position: absolute;
  clip: rect(1px 1px 1px 1px);
  clip: rect(1px, 1px, 1px, 1px);
  padding: 0;
  border: 0;
  height: 1px;
  width: 1px;
  overflow: hidden;
}
</style>

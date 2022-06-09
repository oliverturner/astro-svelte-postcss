<script lang="ts">
  export let href = "#";
  export let title = "title";
  export let body = "body";
</script>

<li class="link-card">
    <a {href}>
        <h2>
            {title}
            <span>&rarr;</span>
        </h2>
        <p>
            {body}
        </p>
    </a>
</li>

<style lang="postcss">
	:root {
		--grad-start: #4f39fa;
		--grad-end: #da62c4;
	  --link-gradient: linear-gradient(
	    45deg,
	    var(--grad-start),
	    var(--grad-end) 30%,
	    var(--color-border) 60%
	  );
	}

	h2 {
	  margin: 0;
	  transition: color 0.6s cubic-bezier(0.22, 1, 0.36, 1);

	  & span {
	    display: inline-block;
	    transition: transform 0.3s cubic-bezier(0.22, 1, 0.36, 1);
	  }
	}

	p {
	  margin-top: 0.75rem;
	  margin-bottom: 0;
	}

	.link-card {
	  display: flex;
	  padding: 0.15rem;
	  background-image: var(--link-gradient);
	  background-size: 400%;
	  border-radius: 0.5rem;
	  background-position: 100%;
	  transition: background-position 0.6s cubic-bezier(0.22, 1, 0.36, 1);

	  &:is(:hover, :focus-within) {
	    background-position: 0;

	    & h2 {
	      color: yellow;

	      & span {
	        transform: translateX(2px);
	      }
	    }
	  }

	  & > a {
	    text-decoration: none;
	    line-height: 1.4;
	    padding: 1em 1.3em;
	    border-radius: 0.35rem;
	    color: var(--text-color);
	    opacity: 0.7;
	  }
	}
</style>

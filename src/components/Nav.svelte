<script>
	export let segment;
</script>

<style type="text/scss">
    .nav { 
		ul {
            margin: 0;
            padding: 0;
            list-style: none;
            text-align: right;
            li {
                display: inline;
                padding: 1rem 2rem;
                &:not(:last-child) {
                    margin-right: -5px;
                }
                a {
                    padding-right: 0 !important;
                    padding-left: 0 !important;
                    border-width: 0 0 2px 0;
                    border-color: rgba(0, 0, 0, 0);
                    border-style: solid;

                    &.selected {
                        border-color: var(--black)
                    }
                }
            }
        }
    }
</style>

<nav class="nav bg-white py-3">
    <ul class="ul">
        <li>
           <a class='{segment === undefined ? "selected" : ""} link' href='.'>Home</a>
        </li>
        <li>
            <a rel=prefetch class='{segment === "blog" ? "selected" : ""} link' href='blog'>Blog</a>
        </li>
    </ul>
</nav>
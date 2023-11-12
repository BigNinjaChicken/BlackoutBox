<script lang="ts">
</script>

<section class="border">
    <aside class="menu">
        <!-- <p class="menu-label mb-3">Black Out Box</p>
        <ul class="menu-list mb-3">
            <li><a class="is-active" href="./">Dashboard</a></li>
        </ul> -->
        <ul class="menu-list mb-3">
            <ul class="menu-list">
                <li>
                    <p class="menu-label">My Game Boxes</p>
                    <ul>
                        <li><a href="./">Box 1</a></li>
                        <li><a href="./">Box 2</a></li>
                        <li><a href="./">Box 3</a></li>
                    </ul>
                </li>
            </ul>
        </ul>
    </aside>
</section>

<style>
    .menu {
        position: sticky;
        display: inline-block;
        vertical-align: top;
        max-height: 100vh;
        overflow-y: auto;
        width: 200px;
        top: 0;
        bottom: 0;
        padding: 30px;
    }

    .border {
        border-right-style: dotted;
    }
</style>

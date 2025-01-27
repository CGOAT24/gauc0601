<script lang="ts">
    export let sha: string;
    export let message: string;
    export let date: string;
    export let url: string;

    const formatDate = (dt: string) => {
        const d = new Date(dt);
		const date = d.toLocaleDateString("fr-CA", {timeZone: "America/New_York"});
		const time = d.toLocaleTimeString("fr-CA", { timeZone: "America/New_York" });
        const formattedTime = time.replace(/\s+/g, "").replace(/min\d+s/, "");
        return `${date} ${formattedTime}`;
    }
</script>
<li>
    <hr />
    <div class="timeline-start">{formatDate(date)}</div>
    <div class="timeline-end timeline-box">
        <div class="dropdown dropdown-hover dropdown-right">
            <div tabindex=0 role="button" class="btn m-1">{message}</div>
            <div class="dropdown-content card card-compact bg-accent text-primary-content z-[1] p-2 shadow">
                <a class="link" href={url} target="_blank">{sha}</a>
            </div>
        </div>
    </div>
    <hr />
</li>

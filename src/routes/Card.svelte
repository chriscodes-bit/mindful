<script lang="ts">
    import { questions } from '../lib/questions';

    let currentQuestion = $state(
        questions[Math.floor(Math.random() * questions.length)]
    );

    function getRandomQuestion() {
        const randomIndex = Math.floor(Math.random() * questions.length);
        currentQuestion = questions[randomIndex];
    }
</script>

<div class="relative w-full max-w-96 h-120 px-4 sm:px-0">
    <!-- Cards behind -->
    <div
        class="absolute inset-x-4 sm:inset-x-0 inset-y-0 translate-x-3 translate-y-3 rotate-2 rounded-2xl border-2 border-slate-950 bg-yellow-300"
    >
        <div class="absolute left-0 right-0 top-12 border-b-2 border-slate-950"></div>
    </div>

    <div
        class="absolute inset-x-4 sm:inset-x-0 inset-y-0 translate-x-1.5 translate-y-1.5 -rotate-4 rounded-2xl border-2 border-slate-950 bg-green-300"
    >
        <div class="absolute left-0 right-0 top-12 border-b-2 border-slate-950"></div>
    </div>

    <!-- Main card -->
    <div
        class="relative w-full h-full rounded-2xl border-2 border-slate-950 bg-violet-300 p-5 sm:p-6 shadow-lg flex flex-col"
    >
        <div class="-mx-5 sm:-mx-6 -mt-5 sm:-mt-6 mb-5 border-b-2 border-slate-950 px-5 sm:px-6 py-4">
            <p
                class="text-sm sm:text-base font-semibold uppercase tracking-widest text-slate-950 text-center rum-raisin-regular"
            >
                {currentQuestion.category}
            </p>
        </div>

        <div class="flex-1 flex items-center justify-center text-center">
            <p
                class="text-xl sm:text-2xl font-semibold leading-relaxed wrap-break-word rum-raisin-regular text-slate-950"
            >
                {currentQuestion.question}
            </p>
        </div>

        <button
            class="mt-6 w-full rounded-xl bg-slate-900 px-5 py-3 font-semibold text-white transition hover:bg-slate-700 active:scale-95 rum-raisin-regular cursor-pointer"
            onclick={getRandomQuestion}
        >
            Zufällige Frage
        </button>
    </div>
</div>
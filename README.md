export default function PercGithubLandingPage() {
  const featureCards = [
    {
      title: "Expression First",
      text: "P.E.R.C. opens with reflection, validates emotion without stigma, and helps users move toward calm, balanced communication.",
    },
    {
      title: "Private Member Access",
      text: "This experience is intended for paying members only, creating a more focused, protected space for personal reflection.",
    },
    {
      title: "SoulWynd Codex Aligned",
      text: "Built on Soul, Signal, and Soil — empathy, integrity, and sustainable pace guide every interaction.",
    },
  ];

  const sideMenu = [
    "New Reflection",
    "Today felt heavy",
    "Help me say this calmly",
    "What am I carrying?",
    "How do I slow down?",
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-[#1a0f0d] via-[#2a160f] to-[#3d1d14] text-stone-100 font-sans">
      <div className="min-h-screen bg-[radial-gradient(ellipse_at_top,rgba(255,180,120,0.12),transparent_60%)]">
        <div className="flex min-h-screen">
          {/* Sidebar */}
          <aside className="hidden lg:flex w-72 flex-col border-r border-white/10 bg-[#1a0f0d]/70 backdrop-blur-xl">
            <div className="px-4 pt-5">
              <button className="w-full rounded-2xl bg-[#fff1dc] px-4 py-3 text-sm font-bold text-[#4d2418] hover:bg-[#ffe6c4] transition-colors shadow-lg shadow-black/20">
                + Start New Reflection
              </button>
            </div>

            <div className="px-4 py-5 space-y-3">
              {sideMenu.map((item) => (
                <button
                  key={item}
                  className="w-full rounded-2xl border border-white/10 bg-white/5 px-4 py-3 text-left text-sm font-medium text-stone-200 hover:bg-white/10 transition-colors"
                >
                  {item}
                </button>
              ))}
            </div>

            <div className="mt-auto p-4 border-t border-white/10">
              <div className="rounded-2xl bg-white/5 px-4 py-4 text-sm text-stone-300">
                <div className="font-bold text-stone-100">P.E.R.C. Membership</div>
                <p className="mt-2 leading-6">
                  Private access for paid users seeking a protected, warm reflection space.
                </p>
              </div>
            </div>
          </aside>

          {/* Main */}
          <main className="flex-1 flex flex-col">
            <header className="border-b border-white/10 bg-[#1d120f]/65 backdrop-blur-xl px-5 md:px-8 py-4 flex items-center justify-between">
              <div>
                <div className="text-2xl md:text-3xl font-black tracking-wide text-[#fff6e9] drop-shadow-sm">
                  P.E.R.C.
                </div>
                <div className="text-sm md:text-base font-medium text-stone-200">
                  Personal Emotional Reflection Companion
                </div>
              </div>

              <div className="flex items-center gap-3">
                <button className="rounded-xl border border-white/15 bg-white/5 px-4 py-2 text-sm font-semibold text-stone-100 hover:bg-white/10 transition-colors">
                  Sign In
                </button>
                <button className="rounded-xl bg-[#fff1dc] px-4 py-2 text-sm font-bold text-[#4d2418] hover:bg-[#ffe6c4] transition-colors shadow-lg shadow-black/20">
                  Member Access
                </button>
              </div>
            </header>

            <section className="px-5 md:px-8 py-8 md:py-10">
              <div className="max-w-6xl mx-auto grid gap-8 xl:grid-cols-[1.2fr_0.8fr] items-start">
                <div className="space-y-8">
                  <div className="rounded-[2rem] border border-white/10 bg-[#241613]/70 backdrop-blur-xl p-6 md:p-8 shadow-2xl shadow-black/30">
                    <p className="text-sm md:text-base font-semibold uppercase tracking-[0.2em] text-amber-200">
                      Generate Balanced Communication
                    </p>
                    <h1 className="mt-3 text-4xl md:text-6xl font-black leading-tight text-[#fff7ea] drop-shadow-sm">
                      Reflect with clarity.
                      <span className="block text-[#ffe2c0]">Respond with balance.</span>
                    </h1>
                    <p className="mt-5 max-w-3xl text-base md:text-lg leading-8 font-medium text-stone-100">
                      P.E.R.C. helps users turn private thoughts into calm, balanced expression. Built with the SoulWynd Codex, this member-based experience supports emotional reflection, healthier communication, and steady self-awareness through empathy, integrity, and sustainable pace.
                    </p>
                    <div className="mt-6 flex flex-wrap gap-3">
                      <span className="rounded-full border border-white/10 bg-white/10 px-4 py-2 text-sm font-semibold text-stone-100">
                        Non-diagnostic
                      </span>
                      <span className="rounded-full border border-white/10 bg-white/10 px-4 py-2 text-sm font-semibold text-stone-100">
                        Private reflection
                      </span>
                      <span className="rounded-full border border-white/10 bg-white/10 px-4 py-2 text-sm font-semibold text-stone-100">
                        Codex-guided support
                      </span>
                    </div>
                  </div>

                  <div className="rounded-[2rem] border border-white/10 bg-[#241613]/70 backdrop-blur-xl shadow-2xl shadow-black/30 overflow-hidden">
                    <div className="border-b border-white/10 px-5 md:px-6 py-4 bg-black/10">
                      <div className="text-lg font-bold text-[#fff6e9]">Reflection Space</div>
                      <div className="text-sm text-stone-300">
                        ChatGPT-style conversation flow for member-only emotional reflection.
                      </div>
                    </div>

                    <div className="px-5 md:px-6 py-6 space-y-6">
                      <div className="flex justify-start">
                        <div className="max-w-2xl rounded-[1.5rem] rounded-bl-md border border-white/10 bg-[#1c120f]/80 px-5 py-4 text-stone-100 shadow-lg shadow-black/20">
                          Hi, I'm here with you. This space is yours — no judgment, no rush. What's been sitting with you today?
                        </div>
                      </div>

                      <div className="flex justify-end">
                        <div className="max-w-2xl rounded-[1.5rem] rounded-br-md bg-gradient-to-r from-red-800 via-orange-700 to-amber-700 px-5 py-4 text-white shadow-lg shadow-black/20 font-medium">
                          I need help putting how I feel into words without sounding reactive.
                        </div>
                      </div>

                      <div className="flex justify-start">
                        <div className="max-w-2xl rounded-[1.5rem] rounded-bl-md border border-white/10 bg-[#1c120f]/80 px-5 py-4 text-stone-100 shadow-lg shadow-black/20">
                          That makes sense. We can slow it down and shape it clearly. Start with one thread: what feels most important to express without losing your balance?
                        </div>
                      </div>
                    </div>

                    <div className="border-t border-white/10 bg-black/10 px-4 md:px-6 py-4">
                      <div className="rounded-[1.75rem] border border-white/10 bg-[#140d0b]/80 p-3 shadow-lg shadow-black/20">
                        <textarea
                          className="w-full min-h-[120px] resize-none rounded-2xl bg-transparent px-4 py-3 text-base font-medium text-stone-100 placeholder:text-stone-400 outline-none"
                          placeholder="Share what is on your mind..."
                        />
                        <div className="mt-3 flex flex-col md:flex-row items-start md:items-center justify-between gap-3">
                          <div className="flex flex-wrap gap-2">
                            {[
                              "Expression first",
                              "Calm guidance",
                              "Clear words",
                              "Private access",
                            ].map((tag) => (
                              <span
                                key={tag}
                                className="rounded-full border border-white/10 bg-white/5 px-3 py-1 text-xs md:text-sm font-semibold text-stone-300"
                              >
                                {tag}
                              </span>
                            ))}
                          </div>
                          <button className="rounded-2xl bg-[#fff1dc] px-5 py-3 text-sm md:text-base font-black text-[#4d2418] hover:bg-[#ffe6c4] transition-colors shadow-lg shadow-black/20">
                            Send Reflection
                          </button>
                        </div>
                      </div>
                      <p className="mt-3 text-center text-xs md:text-sm font-medium text-stone-300">
                        Background images and seasonal artwork can be uploaded later without changing this structure.
                      </p>
                    </div>
                  </div>
                </div>

                <div className="space-y-6">
                  <div className="rounded-[2rem] border border-white/10 bg-[#241613]/70 backdrop-blur-xl p-6 shadow-2xl shadow-black/30">
                    <h2 className="text-xl font-black text-[#fff6e9]">Built from the Codex</h2>
                    <p className="mt-3 text-sm md:text-base leading-7 font-medium text-stone-100">
                      SoulWynd's core trifecta — Soul, Signal, and Soil — shapes every reflection. P.E.R.C. invites expression first, validates emotion without shame, and supports calm, balanced communication at a sustainable pace.
                    </p>
                  </div>

                  <div className="grid gap-4">
                    {featureCards.map((card) => (
                      <div
                        key={card.title}
                        className="rounded-[1.75rem] border border-white/10 bg-[#241613]/70 backdrop-blur-xl p-5 shadow-xl shadow-black/25"
                      >
                        <h3 className="text-lg font-black text-[#fff6e9]">{card.title}</h3>
                        <p className="mt-2 text-sm md:text-base leading-7 font-medium text-stone-100">
                          {card.text}
                        </p>
                      </div>
                    ))}
                  </div>

                  <div className="rounded-[2rem] border border-white/10 bg-gradient-to-br from-[#4d2418]/80 to-[#7b3c24]/70 p-6 shadow-2xl shadow-black/30">
                    <h3 className="text-xl font-black text-[#fff8ed]">Design Directive</h3>
                    <p className="mt-3 text-sm md:text-base leading-7 font-medium text-stone-100">
                      Use strong, bold text with high contrast at all times. All future background photography, leaf textures, or branded fall artwork should be uploaded later as layered assets so the layout remains stable and GitHub-ready now.
                    </p>
                  </div>
                </div>
              </div>
            </section>
          </main>
        </div>
      </div>
    </div>
  );
}

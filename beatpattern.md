setCps(140/60/4)

// PATTERN DEFINITIONS (Scroll past these once written)
// ----------------------------------------------------
const kick = s(`<
  [ [bd ~ ~ ~] [~ ~ ~ ~] [~ ~ ~ ~] [bd ~ bd ~] ]
  [ [~ ~ ~ ~]  [bd ~ ~ ~] [~ ~ ~ ~] [~ ~ ~ ~] ]
  [ [bd ~ ~ ~] [~ ~ bd ~] [~ ~ ~ ~] [bd ~ ~ ~] ]
  [ [~ ~ bd ~] [bd ~ ~ ~] [~ ~ ~ ~] [~ ~ ~ ~] ]
>`).bank("akailinn").gain(0.8)

const rim = s("~ ~ rim ~")
  .bank("alesissr16")
  .gain(0.8)

const hh = s(`<
  [ [hh ~ hh ~] [hh*4 ~ hh*3 ~] [hh ~ hh ~]   [hh ~ hh ~]   ]
  [ [hh ~ hh ~] [hh ~ hh ~]   [hh ~ hh ~]   [hh*4 hh*4 hh*2 ~] ]
  [ [hh ~ hh ~] [hh ~ hh ~]   [hh ~ hh ~]   [hh ~ hh ~]   ]
  [ [hh*4 ~ hh ~] [hh ~ hh ~] [hh ~ hh*3 ~] [hh ~ hh ~]   ]
>`).bank("rolandtr808").gain(0.8)

const sub = note(`<
  [ [c1 ~ ~ ~] [~ ~ ~ ~]  [~ ~ ~ ~] [c1 ~ c1 ~] ]
  [ [~ ~ ~ ~]  [c1 ~ ~ ~] [~ ~ ~ ~] [~ ~ ~ ~]  ]
  [ [c1 ~ ~ ~] [~ ~ c1 ~] [~ ~ ~ ~] [c1 ~ ~ ~] ]
  [ [~ ~ c1 ~] [~ c1 ~ ~] [~ ~ ~ ~] [~ ~ ~ ~]  ]
>`).s("sine").penv(12).pdecay(0.06).decay(0.6).sustain(0).distort(0.3).lpf(120).gain(0.85)


// LIVE MIXER (Toggle single lines here with Ctrl+/ and Alt+Enter)
// ---------------------------------------------------------------
$beat: stack(
  kick,
  rim,
  hh,
  sub,
)._punchcard()

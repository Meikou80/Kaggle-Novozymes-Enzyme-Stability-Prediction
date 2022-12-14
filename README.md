# Kaggle-Novozymes-Enzyme-Stability-Prediction

20221120

とりあえずdiscussionに挙がっているEDAを順に見ていく。
と、その前に内容がよくわからんので用語をdeeplで確認することにした。

1　タンパク質

これは大きなことなので、これを読んでタンパク質を理解するだけでなく...インターネット、youtube、google、教科書などを利用することをお勧めします。これは重要なことで、もっと勉強しても損はないでしょう...そうは言っても...さあどうぞ...
生体分子は生物学で最も重要なものの1つです。生物分子(BIOMOLECULES)の主な種類は以下の4つである。
炭水化物（Carbohydrate
脂質
タンパク質
核酸
タンパク質は、物事を行う役割を担っています。体の中で何かをしているといえば、間違いなくタンパク質が関わっています。
ホロモンはタンパク質
酵素はタンパク質
触媒はタンパク質
ヘモグロビン（血液中の酸素運搬体）
ケラチン(髪の毛)
筋肉(主に)
など
タンパク質はアミノ酸（残基と呼ばれることもある）の鎖でできている
アミノ酸は20種類ある（違いはR基による...ここでは説明しきれない）。
アミノ酸の単位は、他の2つのアミノ酸の単位としか接続できないので、鎖という言葉を使うことに注意（すなわち鎖）
アミノ酸は、炭素原子を中心に、塩基性アミノ基、カルボン酸基、水素原子、R基（側鎖基）が結合したものである。
アミノ酸の構造（特にR基）は、特定のコドン（ヌクレオチドの3連符）によって決定される。
ヌクレオチドは5種類しかありません。
DNAとRNAの両方に含まれるのは3種類（アデニン（A）、シトシン（C）、グアニン（G））。
チミン（T）はDNAにも使われ、ウラシル（U）はRNAに使われます。
タンパク質を作るために、私たちは命令書（DNA/RNA、ヌクレオチド）を使って、一度に1つのアミノ酸を加えることによってタンパク質鎖を構築します（命令書では、各コドン（ヌクレオチドの3連符）が次にどのアミノ酸が来るかを教えてくれます）。また、ある時点では、いつ止めるか（停止コドン）も指示されます。
ここで重要なことは、4つのヌクレオチド（DNAではACTG、RNAではACUG）の組み合わせが一度に3つずつで64通りあり、アミノ酸は20種類しかないので、コードは縮退している（ほとんどの場合、アミノ酸ごとに複数のコドンがある）ことである。
つまり、異なる命令で同じアミノ酸を作ることができるのです。
これはまた、情報は前方には流れず、後方には流れないことを意味する
ヌクレオチド → アミノ酸 ✅（例：CTCとCTTは両方ともロイシンを作る。）
アミノ酸→ヌクレオチド ❌（例：ロイシンはCTCにもCTTにも翻訳できる...が、どちらが本当の由来なのかは分からない）
さて、アミノ酸の鎖がどのように作られるかはわかりましたが、これでは本当の意味でのタンパク質とは言えません。タンパク質を作るには、この長い鎖が折り重なって、非常に複雑な構造になる必要があります。この構造は、4つの複雑なレベルで構成されています。
一次構造とは、アミノ酸が鎖を形成する正確な順序のことです（ここまではほぼ説明したとおりです）。
二次構造とは、ポリペプチドの骨格となる原子間の相互作用により形成される局所的な折り畳み構造のことである。
二次構造には、α-へリックス構造とβ-プリーツシート構造の2種類が存在することが分かっている。
三次構造は、タンパク質の二次構造がさらに折り畳まれることによって生じる。
H-結合、静電気力、ジスルフィド結合、Vander Waals力などがこの構造を安定化させる。
三次構造は、繊維状と球状と呼ばれる2つの主要な分子形状を生じさせる。
四次構造
様々な3次構造の空間的配置により、4次構造が形成される。
ですから、先ほどの「タンパク質を作る」の補足として、鎖が作られるときに、折れ曲がったり、渦巻いたりしながら、3次元構造（3次、4次のレベルまで）が形成されることを理解する必要があるでしょう。
最後に、新しく合成されたタンパク質が採用する最終的な形状は、しばしばタンパク質コンフォメーションと呼ばれ、通常、エネルギー的に最も好ましいものです。
タンパク質は、そのコンフォメーションで存在するとき、しばしば活性であると言われます。
つまり、インスリンは、血液中のグルコースを肝臓、脂肪、骨格筋の細胞に吸収させることによって、炭水化物、脂肪、タンパク質の代謝を調節することができるようになるのです。ワーオ！)
さて、ここまで読んできて、私たちは、タンパク質がどのように作られるのか、何からできているのか、なぜ重要なのか、そして、有用である（活性である）ためには、特定の構造（コンフォメーション）に折りたたまれなければならないことを、おおよそ理解したはずである。

2　タンパク質の安定性

カーンアカデミーのビデオを見る（短いです）→リンク
時間があれば全部のプレイリストを見ることもできます。
タンパク質の立体構造安定性とは、ある特定のタンパク質立体構造（活性状態）が変性に耐えられるかどうかということです。
タンパク質には4段階の構造（一次、二次、三次、四次）があり、これら全てがタンパク質の安定性に寄与していることを忘れないでください。
コンフォメーションとは、タンパク質が最終的に獲得する活性化構造のことであることを忘れないでください。この状態でなければ、タンパク質は正しく機能しません。
変性とは、タンパク質が「壊れる」（結合や力が切れる）ことで、タンパク質が活性化されたコンフォメーションでなくなり、その結果、正しく機能しなくなることを指します。
タンパク質は様々な方法で変性する可能性がありますが、最も一般的なものは以下の通りです（太字の用語は私たちにとって重要です）。
熱
酸(pH)
高濃度の塩分
アルコール
機械的な攪拌
重要な補足：タンパク質は単体では存在せず、溶液の中に同じタンパク質が多数存在する。
タンパク質以外のものはすべて環境と考えよう

3　融点

タンパク質は、1つのタンパク質ではなく、特定のタンパク質の集団として考える必要があることを忘れないでください。
したがって、融解の温度  (Tm)とは、タンパク質集団の50％が変性する（アンフォールドして活性なコンフォメーションが失われる）温度のことです。
したがって、もし温度が指定された  Tm: 50%以上のタンパク質が変性してしまいます。
したがって、もし温度が指定されたTmよりも低ければ、タンパク質の50%以上が変性してしまいます。 
Tm: タンパク質の50％以下が変性する。
そこでELI5の定義する融解温度は  (Tm)は、次のようになる。
集団内のタンパク質の50%以上が機能しなくなる温度（変性/アンフォールディングによる）。
余談。
を実験的に決定することは非常に困難である。 
Tmを実験的に決定することは非常に難しく、アミノ酸配列と環境条件からこの値を予測することは、この分野で非常に重要なテーマとなっている。
また、下の写真から、グランドトゥルース付近の  Tmの値付近では、わずかな温度変化でも大きな影響を受けることがわかる。つまり、間違えるのは簡単だが、正確に当てるのは非常に難しいということだ。

4　ギブス自由エネルギー

計算・測定が非常に困難なためTmを計算・測定することは非常に難しいので、それと相関の高い指標を見つけるというアプローチもあります。このため、我々は  ΔΔG
この競争の文脈では、アンフォールディング自由エネルギー差  (ΔΔG)
  すなわち、ΔΔG = ΔGwildtype - ΔGmutant (単位: kcal/mol)
ギブス自由エネルギーの変化  (ΔΔG) は、タンパク質を折りたたむのに必要なエネルギー量（折りたたまれた状態と折りたたまれてない状態のエネルギー差）に相当する。
一般的に言えば、もし  ΔΔGが必要な場合、同じものを折り畳むのにどれくらいのエネルギーが必要なのかがよくわかると思います。
  
5　ALPHAFOLD2

これまでの定義からわかるように、タンパク質はアミノ酸の鎖が4段階の構造の複雑さ（一次、二次、三次、四次）を特徴とするコンフォメーションに構成されたものである。
実際の立体構造（結合の角度など）を実験的に決定するのは、非常に面倒です
DeepMindは、アミノ酸配列のみから、タンパク質がどのように折り畳まれるかの詳細（角度やその他のあらゆる詳細を含む）を前例のない精度で予測できるツール（実際にはツールのv2）を作成した。
これは、次の2つの理由から、コンペティションにおいて重要です。
テストセットで扱う分子については、AlphaFold2が予測した3次元構造（.pdbファイル）が提供されます。この.pdbファイルは、既存のソリューション/モデルと共に使用することができ、変異が安定性、および/または、分子構造にどのような影響を与えるかを予測することができます。 
tmおよび  δδG
 
 .AlphaFold2は一般に公開されており（オープンソース）、このコンペティションに勝つために必要なトレーニングデータや補足データの作成に極めて重要である可能性があります。
私たちのテスト分子に対するAlphaFold2予測の構造は、この先（および前述のEDAの中で）見ていきます。基本は
原子レベルの情報を得る（1原子あたり1行）
各原子の位置(xyz)
原子の名前
残基番号（どの原子がどのアミノ酸の一部であるかがわかる）
Bファクター(通常のBファクターとは異なる)
AlphaFoldは0から100のスケールで残基ごとの信頼性の推定値を生成します。
この信頼度指標はpLDDTと呼ばれ、lDDT-Cα指標におけるモデルの予測スコアに対応する。
これはダウンロード可能なmmCIFファイルやPDBファイルのB-factorフィールドに格納されています（ただし、B-factorとは異なり、pLDDTは高いほど良好です）。
pLDDTは、3次元構造ビューアにおいて、モデルの残基を色分けするためにも使用されます。

6　DEEPDDG

DeepDDG Serverは、タンパク質の点変異の安定性変化をニューラルネットワークで予測します。
サーバーに必要なもの
分子の3次元構造（コンペティションのホストから提供される.PDBファイル）。
テストセットで表現された一点変異（置換のみ！）または、単純にEVERY POSSIBLE SINGLE POINT MUTATIONの効果を生成し、その後それぞれの値を読み取ります。
ということは  ΔΔGとの相関が高いので  Tmを活用することができる、非常に使い勝手の良いソリューションです。

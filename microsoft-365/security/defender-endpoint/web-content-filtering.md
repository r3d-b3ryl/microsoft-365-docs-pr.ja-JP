---
title: Web コンテンツ フィルタリング
description: Microsoft Defender for Endpointで Web コンテンツ フィルターを使用して、コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制します。
keywords: Web 保護, Web 脅威保護, Web 閲覧, 監視, レポート, カード, ドメインリスト, セキュリティ, フィッシング, マルウェア, エクスプロイト, Web サイト, ネットワーク保護, Edge, Internet Explorer, Chrome, Firefox, Web ブラウザー
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 29a221e60484431722be4e7104efb5b37a0408bc
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648571"
---
# <a name="web-content-filtering"></a>Web コンテンツ フィルタリング

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md)

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

## <a name="what-is-web-content-filtering"></a>Web コンテンツ フィルターとは何ですか?

Web コンテンツ のフィルター処理は、Microsoft Defender for EndpointおよびMicrosoft Defender for Businessの [Web 保護機能](web-protection-overview.md)の一部です。 Web コンテンツ フィルターを使用すると、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡し、規制することができます。 これらの Web サイトの多く (悪意がない場合でも) は、コンプライアンス規制、帯域幅の使用、またはその他の懸念のために問題が発生する可能性があります。

特定のカテゴリをブロックするように、デバイス グループ間でポリシーを構成します。 カテゴリをブロックすると、指定したデバイス グループ内のユーザーがカテゴリに関連付けられている URL にアクセスできなくなります。 ブロックされていないカテゴリの場合、URL は自動的に監査されます。 ユーザーは中断することなく URL にアクセスでき、アクセス統計を収集して、よりカスタム ポリシーの決定を作成するのに役立ちます。 表示しているページ上の要素がブロックされたリソースを呼び出している場合、ユーザーにブロック通知が表示されます。

Web コンテンツ フィルターは、主要な Web ブラウザーで使用できます。Windows Defender SmartScreen (Microsoft Edge) と Network Protection (Chrome、Firefox、Brave、Opera) によって実行されるブロックがあります。 ブラウザーのサポートの詳細については、前提条件に関 [するセクションを参照してください](#prerequisites) 。

## <a name="benefits-of-web-content-filtering"></a>Web コンテンツ フィルター処理の利点

- ユーザーは、オンプレミスでも離れた場所でも、ブロックされたカテゴリの Web サイトにアクセスできなくなります。
- セキュリティ チームは、同じ中央の場所にある Web レポートにアクセスでき、実際のブロックと Web の使用状況を把握できます。
- Defender for Endpoint を使用している場合、セキュリティ チームは[、ロールベースのアクセス制御設定](/microsoft-365/security/defender-endpoint/rbac)で定義されたデバイス グループを使用して、ユーザーのグループにポリシー Microsoft Defender for Endpoint簡単に展開できます。
- Defender for Business を使用している場合は、すべてのユーザーに適用される 1 つの Web コンテンツ フィルター ポリシーを定義できます。 

## <a name="prerequisites"></a>前提条件

この機能を試す前に、次の表に示す要件を満たしていることを確認してください。

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | サブスクリプションには、次のいずれかを含める必要があります。<br/>- [Windows 10/11 Enterprise E5](/windows/deployment/deploy-enterprise-licenses)<br/>- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/e5?activetab=pivot%3aoverviewtab)<br/>- Microsoft 365 E5 Security<br/>- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/enterprise/e3?activetab=pivot%3aoverviewtab)<br/>- [Microsoft Defender for Endpoint プラン 1 またはプラン 2](../defender/eval-defender-endpoint-overview.md)<br/>- [Microsoft Defender for Business](../defender-business/mdb-overview.md)<br/>- [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium)|
| ポータル へのアクセス | <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>にアクセスできる必要があります。 |
| オペレーティング システム | 組織のデバイスは、 [最新のウイルス対策/マルウェア対策更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md)を使用して、次のいずれかのオペレーティング システムを実行している必要があります。 <br/>- Windows 11<br/>- Windows 10 Anniversary Update (バージョン 1607) 以降 |
| 関連する保護 | [Windows Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) と[ネットワーク保護](network-protection.md)は、組織のデバイスで有効にする必要があります。 |

## <a name="data-handling"></a>データの処理

データは、[Microsoft Defender for Endpointデータ処理設定](data-storage-privacy.md)の一部として選択されたリージョンに格納されます。 データは、そのリージョンのデータ センターから離れるわけではありません。 また、お客様のデータは、弊社のデータ プロバイダーを含む第三者と共有されることはありません。

## <a name="turn-on-web-content-filtering"></a>Web コンテンツ フィルターを有効にする

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。

2. ナビゲーション ウィンドウで、**設定[Endpoints** General Advanced Features]\ **(**\>エンドポイント **の**\>一般的\>**な高度な機能\)** を選択します。 

3. **Web コンテンツ のフィルター処理** が表示されるまで下にスクロールします。 

4. トグルを **[オン]** に切り替え、[ **保存] 環境設定** を選択します。

### <a name="configure-web-content-filtering-policies"></a>Web コンテンツ フィルター ポリシーを構成する

Web コンテンツ フィルター ポリシーでは、どのデバイス グループでブロックされるサイト カテゴリを指定します。 ポリシーを管理するには、**設定** \> **Endpoints** \> **Web コンテンツ フィルター** ([**ルール**] の下) に移動します。

ポリシーをデプロイして、次の親または子のカテゴリのいずれかをブロックできます。

<details>
<summary>成人用コンテンツ</summary>

**教団**: メンバーが社会的に受け入れられるものとは異なる信念システムに対する情熱を示すグループや動きに関連するサイト。 

**賭け** 事: オンラインの賭け行為と、賭けのスキルと実践を促進するサイト。

**ヌード**: フルフロントおよび半ヌードの画像またはビデオ (通常は芸術的な形式) を提供し、そのような資料のダウンロードまたは販売を許可するサイト。

**ポルノ/性的に明示的**: 画像ベースまたはテキスト形式の性的に明示的なコンテンツを含むサイト。 性的指向の素材の形式もここに一覧表示されます。

**性教育**: 人間の再現と性行為に関する教育を提供するサイト、性病からの感染防止に関するアドバイスを提供するサイト、性的健康に関するアドバイスを提供するサイトなど、有益で非盗用的な方法で性と性を議論するサイト。

**味なし**: 学校の子どもが閲覧するのに適さないコンテンツに向けられたサイト、または雇用主がスタッフのアクセスに対して不快になるが、必ずしも暴力やポルノではないサイト。

**暴力**: 人間や動物に対する暴力に関連するコンテンツを表示または宣伝するサイト。

</details>

<details>
<summary>高帯域幅</summary>

**サイトのダウンロード**: ユーザーがコンピューター プログラムなどのメディア コンテンツやプログラムをダウンロードできるようにする主な機能を持つサイト。

**画像共有**: 主に写真の検索や共有に使用されるサイト 。これには、ソーシャルな側面を持つものも含まれます。

**ピアツーピア**: ピアツーピア (P2P) ソフトウェアをホストするサイト、または P2P ソフトウェアを使用してファイルの共有を容易にするサイト。

**ストリーミング メディア&ダウンロード**: 主な機能がストリーミング メディアの配布であるサイト、またはユーザーがストリーミング メディアを検索、視聴、またはリッスンできるようにするサイト。
  
</details>

<details>
<summary>法的責任</summary>

**子どもへの不正使用の画像**: 児童の不正使用の画像やポルノを含むサイト。 

**犯罪行為**: 違法行為に関する指示、アドバイス、またはプロモーションを行うサイト。

**ハッキング**: コンピューター ソフトウェアまたはハードウェアの違法または疑問の使用に関するリソースを提供するサイト(割れた著作権で保護された資料を配布するサイトを含む)。

**嫌悪&不寛容**: 人種、宗教、性別、年齢、国籍、身体的障疳、経済状況、性的嗜好、その他の生活習慣の選択によって識別される可能性のある、人口の任意のセクションに関する攻撃的、品位低下、または悪用的な意見を促進するサイト。

**違法な薬物**: 違法または規制された物質を販売するサイト、薬物の乱用を促進するサイト、または関連するパラフェナリアを販売するサイト。

**不正なソフトウェア**: マルウェア、スパイウェア、ボットネット、フィッシング詐欺、著作権盗難の著作権侵害を含むサイト、またはその使用を促進するサイト&。

**学校の不正行為**: 盗用や学校の不正行為に関連するサイト。 

**自傷行為**: ユーザーに対するメッセージの悪用や脅威を含むサイバー攻撃サイトを含む、自傷行為を促進するサイト。

**武器**: 武器を販売するサイト、または武器の使用を主張するサイト (武器、武器、武器、武器など)

</details>

<details>
<summary>レジャー</summary>

**チャット**: 主に Web ベースのチャット ルームであるサイト。

**ゲーム**: ゲームに関連するオンライン サービスや情報のホスティングを通じてゲームを宣伝するサイトを含む、ビデオまたはコンピューター ゲームに関連するサイト。

**インスタント メッセージング: インスタント** メッセージング ソフトウェアまたはクライアント ベースのインスタント メッセージングをダウンロードするために使用できるサイト。

**Professional ネットワーク**: プロフェッショナル ネットワーク サービスを提供するサイト。

**ソーシャル ネットワーク: ソーシャル ネットワーク** サービスを提供するサイト。

**Web ベースのメール**: Web ベースのメール サービスを提供するサイト。
  
</details>

<details>
<summary>未分類</summary>

**新しく登録されたドメイン**: 過去 30 日間に新しく登録され、まだ別のカテゴリに移動されていないサイト。

**パークされたドメイン**: コンテンツがないサイト、または後で使用するためにパークされているサイト。
  
**注**: 未分類には、新しく登録されたドメインとパークされたドメインのみが含まれており、これらのカテゴリ以外の他のすべてのサイトは含まれません。
  
</details>

### <a name="create-a-policy"></a>ポリシーを作成する

新しいポリシーを追加するには、次の手順に従います。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、**設定** > **Web コンテンツ フィルター** **+ ポリシーの追加** を > 選択します。

2. 名前を指定します。

3. ブロックするカテゴリを選択します。 展開アイコンを使用して、各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。

4. ポリシー スコープを指定します。 デバイス グループを選択して、ポリシーを適用する場所を指定します。 選択したデバイス グループ内のデバイスのみが、選択したカテゴリの Web サイトにアクセスできなくなります。

   > [!IMPORTANT]
   > Microsoft 365 Business Premiumまたは Defender for Business のいずれかを使用している場合、Web コンテンツ フィルター ポリシーは既定ですべてのユーザーに適用されます。 スコーピングは適用されません。

5. 概要を確認し、ポリシーを保存します。 ポリシーの更新は、選択したデバイスに適用されるまでに最大 2 時間かかる場合があります。

> [!NOTE]
> - デバイス グループ上のカテゴリを選択せずにポリシーを展開できます。 このアクションは、ブロック ポリシーを作成する前にユーザーの動作を理解するのに役立つ監査のみのポリシーを作成します。
> - ポリシーを削除する場合、またはデバイス グループを同時に変更する場合は、ポリシーの展開が遅れる可能性があります。
> - "Uncategorized" カテゴリをブロックすると、予期しない望ましくない結果が発生する可能性があります。

## <a name="end-user-experience"></a>エンドユーザーのエクスペリエンス

サード パーティでサポートされているブラウザーのブロック エクスペリエンスは、ネットワーク保護によって提供されます。これにより、ブロックされた接続をユーザーに通知するシステム レベルのメッセージが提供されます。 ブラウザー内のユーザー フレンドリなエクスペリエンスを実現するために、Microsoft Edgeの使用を検討してください。

### <a name="allow-specific-websites"></a>特定の Web サイトを許可する

カスタム インジケーター ポリシーを作成することで、Web コンテンツ フィルターでブロックされたカテゴリをオーバーライドして、1 つのサイトを許可することができます。 カスタム インジケーター ポリシーは、対象のデバイス グループに適用されるときに、Web コンテンツ フィルター ポリシーに置き換えられます。

カスタム インジケーターを定義するには、次の手順に従います。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、**エンドポイント** \> **インジケーター** \> **URL/ドメイン** \> **追加項目****設定**\>に移動します。

2. サイトのドメインを入力します。

3. ポリシー アクションを **[許可]** に設定します。

### <a name="dispute-categories"></a>クレーム カテゴリ

誤って分類されたドメインが発生した場合は、Microsoft 365 Defender ポータルから直接カテゴリに異議を申し合うことができます。

ドメインのカテゴリに関する問題を解決するには、 **レポート** \> **Web 保護** \> **Web コンテンツ フィルターの詳細** \> **ドメイン** に移動します。 Web コンテンツ フィルター レポートの [ドメイン] タブに、各ドメインの横に省略記号が表示されます。 この省略記号にマウス ポインターを合わせ、[ **クレーム カテゴリ**] を選択します。

パネルが開き、優先度を選択し、再集計に推奨されるカテゴリなどの詳細を追加できます。 フォームに入力したら、[送信] を選択 **します**。 チームは、1 営業日以内に要求を確認します。 すぐにブロックを解除する場合は、 [カスタム許可インジケーター](indicator-ip-domain.md)を作成します。

## <a name="web-content-filtering-cards-and-details"></a>Web コンテンツ フィルター カードと詳細

[レポート **Web 保護****]** \> を選択して、Web コンテンツのフィルター処理と Web 脅威の保護に関する情報を含むカードを表示します。 次のカードは、Web コンテンツ のフィルター処理に関する概要情報を提供します。

### <a name="web-activity-by-category"></a>カテゴリ別の Web アクティビティ

このカードには、アクセス試行回数の増減が最も多い親 Web コンテンツ カテゴリが一覧表示されます。 過去 30 日間、3 か月、または 6 か月間の組織内の Web アクティビティ パターンの大幅な変化について理解します。 詳細を表示するには、カテゴリ名を選択します。

この機能を使用した最初の 30 日間は、組織にこの情報を表示するのに十分なデータがない可能性があります。

:::image type="content" source="images/web-activity-by-category600.png" alt-text="カテゴリ カード別の Web アクティビティ" lightbox="images/web-activity-by-category600.png":::

### <a name="web-content-filtering--summary-card"></a>Web コンテンツ フィルターの概要カード

このカードには、さまざまな親 Web コンテンツ カテゴリに対するブロックされたアクセス試行の分布が表示されます。 色付きのバーのいずれかを選択すると、特定の親 Web カテゴリに関する詳細情報が表示されます。

:::image type="content" source="images/web-content-filtering-summary.png" alt-text="Web コンテンツ フィルターの概要カード" lightbox="images/web-content-filtering-summary.png":::

### <a name="web-activity-summary-card"></a>Web アクティビティの概要カード

このカードには、すべての URL 内の Web コンテンツに対する要求の合計数が表示されます。

:::image type="content" source="images/web-activity-summary.png" alt-text="Web アクティビティの概要カード" lightbox="images/web-activity-summary.png":::

### <a name="view-card-details"></a>カードの詳細を表示する

カード内のグラフからテーブル行または色付きバーを選択すると、各カードの **レポートの詳細** にアクセスできます。 各カードのレポートの詳細ページには、Web コンテンツ カテゴリ、Web サイト ドメイン、およびデバイス グループに関する広範な統計データが含まれています。

:::image type="content" source="images/web-protection-report-details.png" alt-text="Web 保護レポートの詳細" lightbox="images/web-protection-report-details.png":::

- **Web カテゴリ**: 組織内でアクセス試行があった Web コンテンツ カテゴリを一覧表示します。 特定のカテゴリを選択して、概要ポップアップを開きます。

- **ドメイン**: 組織内でアクセスまたはブロックされた Web ドメインを一覧表示します。 特定のドメインを選択すると、そのドメインに関する詳細情報が表示されます。

- **デバイス グループ**: 組織内で Web アクティビティを生成したすべてのデバイス グループを一覧表示します

ページの左上にある時間範囲フィルターを使用して、期間を選択します。 情報をフィルター処理したり、列をカスタマイズしたりすることもできます。 選択した項目に関する詳細情報を含むポップアップ ウィンドウを開くには、行を選択します。

### <a name="known-issues-and-limitations"></a>既知の問題と制限事項

デバイスの OS 構成がサーバー (**cmd** \> **Systeminfo** \> **OS 構成**) の場合にのみ、Microsoft Edgeがサポートされます。 Network Protection は、サポートされているサード パーティのブラウザー間のトラフィックのセキュリティ保護を担当するサーバー デバイスの検査モードでのみサポートされます。

Microsoft Edgeのみがサポートされ、azure Virtual Desktop マルチセッション ホストWindows 10ネットワーク保護はサポートされていません。

ネットワーク保護は現在 SSL 検査をサポートしていないため、通常はブロックされる Web コンテンツ フィルターによって一部のサイトが許可される可能性があります。 TLS ハンドシェイクが行われた後の暗号化されたトラフィックの可視性が不足し、特定のリダイレクトを解析できないため、サイトは許可されます。  これには、一部の Web ベースのメール ログイン ページからメールボックス ページへのリダイレクトが含まれます。 受け入れられた回避策として、ログイン ページのカスタム ブロック インジケーターを作成して、ユーザーがサイトにアクセスできないようにすることができます。 これにより、同じ Web サイトに関連付けられている他のサービスへのアクセスがブロックされる可能性があることに注意してください。 

Microsoft 365 Business PremiumまたはMicrosoft Defender for Businessを使用している場合は、環境に対して 1 つの Web コンテンツ フィルター ポリシーを定義できます。 このポリシーは、既定ですべてのユーザーに適用されます。

## <a name="see-also"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
- [Web の脅威への対応](web-protection-response.md)
- [Network Protection の要件](web-content-filtering.md)

---
title: Microsoft Defender のパイロットOffice 365、実稼働環境で評価を使用する
description: Microsoft Defender の機能を適切にテストするために、アクティブユーザーと既存のユーザーのグループを使用して評価をOffice 365。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: d8cd0132c8b02ae29cf49c9a700a868fa3a93554
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64501357"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>パイロット Microsoft Defender for Office 365

**適用対象:**
- Microsoft 365 Defender

この記事は[、Microsoft Defender の](eval-defender-office-365-overview.md)評価環境を設定するプロセスの手順 3/3 Office 365。 このプロセスの詳細については、概要の記事を [参照してください](eval-defender-office-365-overview.md)。

次の手順を使用して、Microsoft Defender のパイロットをセットアップして構成Office 365。

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="Microsoft Defender for microsoft Defender でパイロットを作成する手順は、Office 365です。" lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [手順 1: パイロット グループを作成する](#step-1-create-pilot-groups)
- [手順 2: 保護の構成](#step-2-configure-protection)
- [手順 3: 機能を試す - シミュレーション、監視、およびメトリックについて理解する](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

Microsoft Defender for Office 365を評価する場合は、組織全体のポリシーを有効にし、適用する前に、特定のユーザーをパイロットに選択できます。 配布グループを作成すると、展開プロセスの管理に役立ちます。 たとえば、*defender for Office 365 Users - Standard Protection*、*Defender for Office 365 Users - Strict Protection*、*Defender for Office 365 Users - Custom Protection*、Defender for *Office 365 Users - Exceptions* などのグループを作成します。

「Standard」と「Strict」がこれらのグループで使用される用語である理由は明らかではないかもしれませんが、Defender for Office 365 セキュリティ プリセットについて詳しく説明すると明らかになります。 名前付けグループ 'custom' と 'exceptions' は自分自身を表しますが、ほとんどのユーザーは標準および厳密なカスタムグループと例外グループに該当する必要があります。リスクの管理に関して貴重なデータを収集します。

## <a name="step-1-create-pilot-groups"></a>手順 1: パイロット グループを作成する

配布グループは、オンプレミスの Active Directory Exchange Onlineで直接作成および定義できます。

1. 受信者管理者の役割がExchangeグループ管理アクセス許可が委任されたアカウントを使用して、管理者センター (EAC) にサインインします。
2. ナビゲーション メニューで、[受信者] を *展開し、[* グループ] を *選択します*。

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" クリックする [グループ] メニュー項目" lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. [グループ] ダッシュボードで、[グループの追加] を選択します。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="[グループの追加] オプションをクリックする" lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. グループの種類の場合は、[配布] *を選択し、[* 次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" [グループの種類の選択] セクション" lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. グループに名前と説明を付け、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="[基本の設定] セクション" lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

## <a name="step-2-configure-protection"></a>手順 2: 保護の構成

Defender for Office 365の一部の機能は既定で構成およびオンになっていますが、セキュリティ操作では、保護のレベルを既定から上げる必要があります。

一部の機能 *はまだ構成* されていません。 保護を構成するには、次の 3 つのオプションがあります。

- **事前設定されたセキュリティ ポリシーを** 自動的に割り当てる- [すべての](../office-365-security/preset-security-policies.md) 機能に対して一様なレベルの保護をすばやく割り当てる方法として、事前設定されたセキュリティ ポリシーが提供されます。 standard_ または **___ strict *から選択*_できます_**。 優れた方法は、事前に設定されたセキュリティ ポリシーから始め、機能と独自の脅威環境について詳しくは、ポリシーを微調整する方法です。 ここでの利点は、ユーザーのグループを可能な限り迅速に保護し、後で保護を調整できるという利点があります。 (このメソッドをお勧めします。
- **ベースライン保護を手動** で構成する - 環境を自分で構成する場合は、「脅威から保護する」のガイダンスに従って、迅速に保護の基準 [を達成できます](../office-365-security/protect-against-threats.md)。 この方法では、構成可能な設定の詳細を確認できます。 また、後でポリシーを微調整することもできます。
- **カスタム *保護* ポリシーを構成する** - 評価の一環としてカスタム保護ポリシーを作成して割り当てできます。 ポリシーのカスタマイズを開始する前に、これらの保護ポリシーが適用および適用される優先順位を理解することが重要です。 セーフ リンクと添付ファイルのセキュリティ ポリシーを定義するには、特定の設定が適用されている場合でも、一部のポリシーを作成セーフがあります。
> [!IMPORTANT]
> **カスタム保護ポリシーを** 構成する必要がある場合は、標準と厳密なセキュリティ定義を構成する値を確認する必要があります。*[EOP と Microsoft Defender](../office-365-security/recommended-settings-for-eop-and-office365.md)* の Office 365 セキュリティに関する推奨設定。 構成が行う前に表示される既定値も一覧表示されます。 カスタム ビルドの場所を表すスプレッドシートを保持します。

### <a name="assign-preset-security-policies"></a>事前設定されたセキュリティ ポリシーの割り当て

MDO を評価する際には、まず推奨されるベースライン ポリシーを使用し、評価期間の間に必要に応じて絞り込む必要があります。

推奨される EOP と Defender を、Office 365保護ポリシーに対して迅速に有効にし、評価の一環として特定のパイロット ユーザーまたは定義されたグループに割り当てできます。 事前設定されたポリシーは、基準 **標準** 保護テンプレートまたはより積極的な **厳密** な保護テンプレートを提供します。これは個別に割り当て、または組み合わせることができます。

手順の詳細[については、EOP と Microsoft Defender](../office-365-security/preset-security-policies.md) の事前設定Office 365を示します。

1. テナントにログオンMicrosoft 365します。 Office 365 の組織の管理役割に追加された Microsoft 365 Defender ポータルへのアクセス権を持つアカウントを使用するか、Microsoft 365 でセキュリティ管理者の役割を使用します。
2. ナビゲーション メニューから、[電子メールとグループ& *ポリシー] の* 下の [ポリシー&選択します。

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text=" [ポリシー] &ルール] メニュー項目をクリックします。" lightbox="../../media/mdo-eval/5_mdo-eval-pilot-policies.png":::

3. [ポリシー の設定] &ダッシュボードで、[脅威 *ポリシー] をクリックします*。

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text=" [脅威ポリシー] メニュー項目をクリックする" lightbox="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png":::

4. このポータルMicrosoft 365 Defenderナビゲーション メニューから [脅威の管理] を展開し、サブメニューから [ポリシー] を選択します。
5. [ポリシー] ダッシュボードで、[セキュリティ ポリシーの *事前設定] をクリックします*。

   :::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="脅威ポリシーの種類" lightbox="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png":::

6. [ *編集] を* クリックして、標準ポリシーまたは厳密なポリシーを構成および割り当てる。

   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="[事前設定されたセキュリティ ポリシー] ページの各種ポリシーに適用されるさまざまな設定" lightbox="../../media/mdo-eval/8-mdo-eval-pilot-preset.png":::

7. 必要に応じて、特定のパイロット ユーザーまたはユーザー のグループに基準 ***EOP** _ 保護を適用する条件を追加し、[_Next*] を選択して続行します。

   *たとえば、Office 365 Standard Protection* グループの定義された Defender のメンバーである受信者がグループにアカウントを追加するか、グループからアカウントを削除することによって管理される場合、パイロット評価用の Office 365 の Defender 条件を適用できます。

   :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="EOP 保護と見なされるポリシー" lightbox="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png":::

8. 必要に応じて、ベースライン ***MDO** _ 保護を特定のパイロット ユーザーまたはユーザー のグループに適用する条件を追加します。 [_Next*] をクリックして続行します。

   たとえば、パイロット評価の Office 365 条件の Defender は、受信者が *定義された Office 365 Standard Protection* グループの Defender のメンバーであり、グループを介してアカウントを追加/削除することによって管理される場合に適用できます。

   :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="セキュリティ保護の防御とOffice 365ポリシー" lightbox="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png":::

9. 事前設定されたセキュリティ ポリシーを割り当てる変更を確認して確認します。
10. Microsoft 365 Defender ポータル > ポリシー & ルール > 脅威ポリシー > に戻り、[事前設定されたセキュリティ ポリシー] タイルをクリックすることで、事前設定された保護ポリシーを管理できます (再構成、再適用、無効化など)。

### <a name="configure-custom-protection-policies"></a>カスタム保護ポリシーの構成

ポリシー テンプレート用の *定義済みの Standard* または *Strict* Defender Office 365、パイロット ユーザーに推奨されるベースライン保護を提供します。 ただし、評価の一環としてカスタム保護ポリシーを作成および割り当てできます。

これらの保護 *ポリシーは*、電子メール保護の順序と優先順位として適用および適用される場合の優先順位に注意することが重要です。[Office 365説明します](../office-365-security/how-policies-and-protections-are-combined.md)。

次の表は、カスタム保護ポリシーの構成と割り当てに関するリファレンスとガイダンスを示しています。

<br>

****

|ポリシー|説明|Reference|
|:---:|---|---|
|接続フィルター|IP アドレスを使用して、適切または悪い送信元メール サーバーを識別します。|[EOP で既定の接続フィルター ポリシーを構成する](../office-365-security/configure-the-connection-filter-policy.md)|
|マルウェア対策|ユーザーを電子メール マルウェアから保護します。その中には、実行するアクションやマルウェアが検出された場合に通知するユーザーが含されます。|[EOP でマルウェア対策ポリシーを構成する](../office-365-security/configure-anti-malware-policies.md)|
|スプーフィング対策|スプーフィング インテリジェンスとスプーフィング インテリジェンスの分析情報を使用して、スプーフィングの試行からユーザーを保護します。|[Defender でスプーフィング インテリジェンスを構成Office 365](../office-365-security/learn-about-spoof-intelligence.md)|
|スパム対策|スパムが検出された場合に実行するアクションを含む、電子メール スパムからユーザーを保護します。|[Defender でスパム対策ポリシーを構成する (Office 365](../office-365-security/configure-your-spam-filter-policies.md)|
|フィッシング対策|フィッシング攻撃からユーザーを保護し、疑わしいメッセージの安全に関するヒントを構成する|[詳細については、「Microsoft Defender for Office 365 のフィッシング詐欺対策ポリシーを構成する」を参照してください。](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|安全な添付ファイル|メールの添付ファイルやファイル内の悪意のあるコンテンツからユーザーを保護SharePoint、OneDrive、Teams。|[Defender for Office 365](../office-365-security/set-up-safe-attachments-policies.md)|
|安全なリンク|電子メール メッセージやデスクトップ アプリで悪意のあるリンクを開いて共有Office保護します。|[Defender でセキュリティで安全なリンク ポリシーを設定Office 365](../office-365-security/set-up-safe-links-policies.md)|
|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>手順 3: 機能を試して、シミュレーション、監視、およびメトリックを理解する

パイロットがセットアップおよび構成されたので、Microsoft Defender for Microsoft 365 に固有のレポート、監視、攻撃シミュレーション ツールを理解すると便利です。

<br>

****

|機能|説明|詳細情報|
|---|---|---|
|脅威エクスプローラー|Threat Explorer は、セキュリティ運用チームが脅威を調査して対応し、Office 365 の電子メールやファイルのマルウェアやフィッシングの疑いについての情報、および組織に対する他のセキュリティ上の脅威やリスクを表示するのに役立つ強力なリアルタイム ツールです。|[脅威エクスプローラーとリアルタイムの検出のビュー](../office-365-security/threat-explorer-views.md)|
|攻撃シミュレーター|Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングを使用すると、組織内で現実的な攻撃シナリオを実行できます。これは、実際の攻撃が環境に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。|[攻撃シミュレーション トレーニングの使用を開始する](../office-365-security/attack-simulation-training-get-started.md)|
|レポート ダッシュボード|左側のナビゲーション メニューで、[レポート] をクリックし、[メール] グループ&展開します。 メール & コラボレーション レポートでは、セキュリティの傾向を特定し、その中には [送信に移動] などのアクションを実行できるものや、メールフローの状態の概要、トップ マルウェア、スプーフィング検出、侵害されたユーザー、メール遅延、セーフ リンク、セーフ 添付ファイル レポートなどの傾向を表示するアクションを実行できるレポートがあります。 これらの指標は自動的に生成されます。|[レポートの表示](../office-365-security/view-email-security-reports.md)|
|

## <a name="next-steps"></a>次の手順

[Microsoft Defender for Endpoint の評価](eval-defender-endpoint-overview.md)

[Microsoft [Defender for Office 365](eval-defender-office-365-overview.md)

[評価とパイロット] [の概要に戻Microsoft 365 Defender](eval-overview.md)

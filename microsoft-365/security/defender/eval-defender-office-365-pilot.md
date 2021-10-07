---
title: Microsoft Defender をパイロットOffice 365、実稼働環境で評価を使用する
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
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: ef91bf7b4d3cdb2e4e335215a3b4f068ccdfe645
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198111"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>パイロット Microsoft Defender for Office 365
**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender の評価環境を設定するプロセスの手順[3/3](eval-defender-office-365-overview.md) Office 365。 このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-office-365-overview.md)。

次の手順を使用して、Microsoft Defender のパイロットをセットアップして構成Office 365。

![Microsoft Defender のパイロットを作成する手順をOffice 365。](../../media/defender/m365-defender-office-pilot.png)

- [手順 1: パイロット グループを作成する](#step-1-create-pilot-groups)
- [手順 2: 保護の構成](#step-2-configure-protection)
- [手順 3: 機能を試す - シミュレーション、監視、およびメトリックについて理解する](#step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics)

Microsoft Defender for Office 365を評価する場合は、組織全体でポリシーを有効にし、適用する前に、特定のユーザーのパイロットを選択できます。 配布グループを作成すると、展開プロセスの管理に役立ちます。 たとえば *、Office 365 ユーザー* 向け Defender - Standard Protection、Defender *for Office 365 Users - Strict Protection、Defender* for Office 365 Users - Custom *Protection、* または Defender for *Office 365 Users - Exceptions* などのグループを作成します。

'Standard' と 'Strict' がこのために使用される用語である理由は明らかではないかもしれませんが、Defender for Office 365 セキュリティ プリセットについて詳しく説明すると明らかになります。 名前付けグループ 'custom' と 'exceptions' は自分自身を表しますが、ほとんどのユーザーは標準および厳密に該当する必要があります。カスタム グループと例外グループは、リスクの管理に関して貴重なデータを収集します。

## <a name="step-1-create-pilot-groups"></a>手順 1: パイロット グループを作成する

配布グループは、オンプレミスの Active Directory Exchange Onlineで直接作成および定義できます。

1. 受信者管理者のExchangeまたはグループ管理のアクセス許可が委任されたアカウントを使用して、管理者センター (EAC) にログオンします。
2. ナビゲーション メニューで、[受信者] を *展開し、[* グループ] を *選択します*。

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text="Exchangeメニュー (クイック起動) で管理センターを開き、グループを指す矢印を表示します。[グループ] をクリックします。":::

3. [グループ] ダッシュボードで、[グループの追加] を選択します。

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="[グループ] パネルにグループを追加します。":::

4. グループの種類の場合は、[配布] *を選択し、[* 次へ] をクリックします。

:::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text="ここで配布グループの種類を選択します。":::

5. グループに名前と説明を付け、[次へ] をクリックします。

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="グループに名前を付け、説明します。":::

## <a name="step-2-configure-protection"></a>手順 2: 保護の構成

Defender for Office 365の一部の機能は、既定で構成およびオンになっていますが、セキュリティ操作では、既定の保護レベルを上げる必要があります。

一部の機能 *はまだ構成* されていません。 保護を構成するには、次の 3 つのオプションがあります。

- **事前に設定されたセキュリティ ポリシー** を自動的に割り当てる [—](../office-365-security/preset-security-policies.md) すべての機能に一様なレベルの保護を迅速に割り当てる方法として、事前設定されたセキュリティ ポリシーが提供されます。 標準 _ または **__ strict_*から選択*_できます_**。 優れた方法は、事前に設定されたセキュリティ ポリシーから始め、機能と独自の脅威環境について詳しくは、ポリシーを微調整する方法です。 ここでの利点は、ユーザーのグループを可能な限り迅速に保護し、後で保護を調整できるという利点があります。 (このメソッドをお勧めします。
- **ベースライン保護を手動で** 構成する - 環境を自分で構成する場合は、「脅威から保護する」のガイダンスに従って、迅速に保護の基準 [を達成できます](../office-365-security/protect-against-threats.md)。 この方法では、構成可能な設定の詳細を確認できます。 もちろん、後でポリシーを微調整することもできます。
- **カスタム *保護* ポリシーの構成** - 評価の一環としてカスタム保護ポリシーを作成して割り当てできます。 ポリシーのカスタマイズを開始する前に、これらの保護ポリシーが適用および適用される優先順位を理解することが重要です。 セーフ リンクと添付ファイルのセキュリティ ポリシーを定義するには、特定の設定が適用されている場合でも、一部のポリシーを作成セーフがあります。

> [!IMPORTANT]
> **カスタム保護ポリシー** を構成する必要がある場合は、ここで Standard および Strictセキュリティ定義を構成する値を調べる必要があります。EOP および *[Microsoft Defender](../office-365-security/recommended-settings-for-eop-and-office365.md)* のセキュリティに関する推奨設定をOffice 365します。 構成が行う前に表示される既定値も一覧表示されます。 カスタム ビルドの場所を表すスプレッドシートを保持します。

### <a name="assign-preset-security-policies"></a>事前設定されたセキュリティ ポリシーの割り当て

MDO を評価する際に推奨されるベースライン ポリシーから始め、評価期間中に必要に応じて絞り込む必要があります。

推奨される EOP と Defender は、Office 365保護ポリシーに対して迅速に有効にし、評価の一環として特定のパイロット ユーザーまたは定義されたグループに割り当てできます。 事前設定されたポリシーは、基準 **標準** 保護テンプレートまたはより積極的な **厳密** な保護テンプレートを提供し、個別に割り当て、または組み合わせることができます。

手順の詳細[については、EOP](../office-365-security/preset-security-policies.md)と Microsoft Defender のOffice 365のセキュリティ ポリシーを示します。

1. テナントにログオンMicrosoft 365します。 Office 365 の組織の管理役割に追加された Microsoft 365 Defender ポータルへのアクセス権を持つアカウントを使用するか、Microsoft 365 でセキュリティ管理者の役割を使用します。
2. ナビゲーション メニューから、[電子メールとグループ& *ポリシー] の* 下の [ポリシー&選択します。

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text="ナビゲーション パネルの [&グループ] で、[ポリシー] をクリックして、&します。":::

3. [ポリシー の設定] &ダッシュボードで、[脅威 *ポリシー] をクリックします*。

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text="a.":::

4. このポータルMicrosoft 365 Defenderナビゲーション メニューから [脅威の管理] を展開し、サブメニューから [ポリシー] を選択します。
5. [ポリシー] ダッシュボードで、[セキュリティ ポリシーの *事前設定] をクリックします*。

:::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="[事前設定されたセキュリティ ポリシー] タイルをクリックします。":::

6. [ *編集] を* クリックして、標準ポリシーまたは厳密なポリシーを構成および割り当てる。 :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="[事前設定されたセキュリティ ポリシー] パネルで、[編集] をクリックします。":::
7. 必要に応じて、特定のパイロット ユーザーまたはユーザーのグループに基準 ***EOP** _ 保護を適用する条件を追加し、続行するには [_Next*] を選択します。
    - *たとえば、Office 365* Standard Protection グループの定義された Defender のメンバーである受信者がグループにアカウントを追加または削除するだけで管理される場合、パイロット評価用の Office 365 の Defender 条件を適用できます。
 :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="パイロット グループに EOP セキュリティ レベルを適用するために必要な条件を追加します。":::

8. 必要に応じて、ベースライン ***MDO** _ 保護を特定のパイロット ユーザーまたはユーザー のグループに適用する条件を追加します。 [_Next*] をクリックして続行します。
    - *たとえば、Office 365* Standard Protection グループの定義された Defender のメンバーである受信者がグループ経由でアカウントを追加/削除するだけで管理される場合、パイロット評価の Office 365 の Defender 条件を適用できます。
  :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="セキュリティ レベルに対して Defender を適用するために必要Office 365条件をパイロット グループに追加します。":::

9. 事前設定されたセキュリティ ポリシーを割り当てる変更を確認して確認します。
10. Microsoft 365 Defender ポータル > ポリシー & ルール > 脅威ポリシー > に戻り、[事前設定されたセキュリティ ポリシー] タイルをクリックすることで、事前設定された保護ポリシーを管理 (再構成、再適用、無効化など) できます。

### <a name="configure-custom-protection-policies"></a>カスタム保護ポリシーの構成

ポリシー テンプレート用の定義済みの *Standard* または *Strict* Defender Office 365、パイロット ユーザーに推奨されるベースライン保護を提供します。 ただし、評価の一環としてカスタム保護ポリシーを作成および割り当てできます。

これらの保護 *ポリシーが* 適用および適用される場合の優先順位に注意することが重要です。電子メール保護の順序と優先順位 [-](../office-365-security/how-policies-and-protections-are-combined.md) Office 365説明します。

次の表は、カスタム保護ポリシーの構成と割り当てに関するリファレンスと追加のガイダンスを示しています。

|ポリシー   |説明  |リファレンス  |
|:---------:|---------|---------|
|接続フィルター     |    IP アドレスを使用して、適切または悪い送信元メール サーバーを識別します。     |     [EOP で既定の接続フィルター ポリシーを構成する](../office-365-security/configure-the-connection-filter-policy.md)    |
|マルウェア対策    |    ユーザーを電子メール マルウェアから保護します。その中には、実行するアクションやマルウェアが検出された場合に通知するユーザーが含されます。     |    [EOP でマルウェア対策ポリシーを構成する](../office-365-security/configure-anti-malware-policies.md)     |
|スプーフィング対策     |  スプーフィング インテリジェンスとスプーフィング インテリジェンスの分析情報を使用して、スプーフィングの試行からユーザーを保護します。   |     [Defender でスプーフィング インテリジェンスを構成Office 365](../office-365-security/learn-about-spoof-intelligence.md)    |
|スパム対策     |    スパムが検出された場合に実行するアクションを含む、電子メール スパムからユーザーを保護します。     |    [Defender でスパム対策ポリシーを構成する方法をOffice 365](../office-365-security/configure-your-spam-filter-policies.md)     |
|フィッシング対策     |   フィッシング攻撃からユーザーを保護し、疑わしいメッセージの安全に関するヒントを構成する      |     [詳細については、「Microsoft Defender for Office 365 のフィッシング詐欺対策ポリシーを構成する」を参照してください。](../office-365-security/configure-mdo-anti-phishing-policies.md)    |
|安全な添付ファイル     |    メールの添付ファイルやファイル内の悪意のあるコンテンツからユーザーを保護SharePoint、OneDrive、Teams。     |    [Defender for Office 365](../office-365-security/set-up-safe-attachments-policies.md)     |
|安全なリンク     |     電子メール メッセージやデスクトップ アプリで悪意のあるリンクを開いて共有Office保護します。    |    [Defender for Office 365](../office-365-security/set-up-safe-links-policies.md)     |

## <a name="step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics"></a>手順 3: 機能を試す - シミュレーション、監視、およびメトリックについて理解する

パイロットがセットアップおよび構成されたので、Microsoft Defender for Microsoft 365 に固有のレポート、監視、および攻撃のシミュレーション ツールを理解すると便利Microsoft 365。

|機能  |説明  |詳細情報  |
|---------|---------|---------|
|脅威エクスプローラー     | Threat Explorer は、セキュリティ運用チームが脅威を調査して対応し、Office 365 の電子メールやファイルのマルウェアやフィッシングの疑いについての情報、および組織に対する他のセキュリティ上の脅威やリスクを表示するのに役立つ、リアルタイムに近い強力なツールです。        | [脅威エクスプローラーのビューとリアルタイム検出 ](../office-365-security/threat-explorer-views.md)       | 
|攻撃シミュレーター     | Microsoft Defender 365 ポータルの攻撃シミュレーション トレーニングを使用して、実際の攻撃が環境に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立つ現実的な攻撃シナリオを組織で実行できます。        |  [Microsoft Defender の攻撃Office 365](../office-365-security/attack-simulator.md)       |
|レポート ダッシュボード     | 左側のナビゲーション メニューで、[レポート] をクリックし、[メール] &を展開します。 電子メール & コラボレーション レポートでは、セキュリティの傾向を特定し、その中には [送信に移動] などのボタンを使用してアクションを実行できるものや、メールフローの状態の概要、トップ マルウェア、スプーフィング検出、侵害されたユーザー、メール遅延、セーフ リンク、セーフ 添付ファイル レポートなどの傾向を表示するアクションを実行できるレポートがあります。 これらの指標は自動的に生成されます。  |    [レポートの表示](../office-365-security/view-email-security-reports.md)     |

## <a name="next-steps"></a>次の手順


[Microsoft Defender for Endpoint の評価](eval-defender-endpoint-overview.md)

[Microsoft Defender for Office 365 の評価[] の概要に戻Office 365](eval-defender-office-365-overview.md)

[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)
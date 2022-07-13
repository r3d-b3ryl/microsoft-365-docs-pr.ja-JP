---
title: パイロット Microsoft Defender for Office 365、運用環境で評価を使用する
description: Microsoft Defender for Office 365の機能を適切にテストするために、アクティブユーザーと既存のユーザーのグループで評価をパイロットする手順。
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
- zerotrust-solution
ms.custom: admindeeplinkEXCHANGE
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: fb246805ebf38cddfda6fe308d19e1dd1419531b
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66748805"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>パイロット Microsoft Defender for Office 365

**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Office 365の評価環境を設定する手順 [3/3](eval-defender-office-365-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-office-365-overview.md)関する記事を参照してください。

次の手順に従って、Microsoft Defender for Office 365のパイロットを設定して構成します。

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="Microsoft Defender for Office 365 ポータルでパイロットを作成する手順" lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [手順 1: パイロット グループを作成する](#step-1-create-pilot-groups)
- [手順 2: 保護を構成する](#step-2-configure-protection)
- [手順 3: 機能を試す - シミュレーション、監視、メトリックについて理解する](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

Microsoft Defender for Office 365を評価する場合は、組織全体のポリシーを有効にして適用する前に、特定のユーザーをパイロットすることを選択できます。 配布グループを作成すると、デプロイ プロセスの管理に役立ちます。 たとえば、*Defender for Office 365 ユーザー - Standard Protection*、*Defender for Office 365 Users - Strict Protection*、*Defender for Office 365 Users - Custom Protection*、Defender for Office 365などのグループを作成します。*ユーザー - 例外*。

"Standard" と "Strict" がこれらのグループに使用されている用語である理由は明らかではないかもしれませんが、セキュリティ プリセットDefender for Office 365詳しく調べると明確になります。 名前付けグループ 'custom' と 'exception' は自分で話します。ただし、ほとんどのユーザーは *標準* および *厳格な* カスタムグループと例外グループに該当する必要がありますが、リスクの管理に関する貴重なデータが収集されます。

## <a name="step-1-create-pilot-groups"></a>手順 1: パイロット グループを作成する

配布グループは、Exchange Onlineで直接作成および定義することも、オンプレミスの Active Directoryから同期することもできます。

1. 受信者管理者ロールが付与されているか、グループ管理アクセス許可が委任されているアカウントを使用して、Exchange 管理 センター (EAC) にサインインします。
2. ナビゲーション メニューの [ *受信者]* を展開し、[ *グループ*] を選択します。

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" クリックする [グループ] メニュー項目" lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. [グループ] ダッシュボードで、[グループの追加] を選択します。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="クリックする [グループの追加] オプション" lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. グループの種類については、[ *配布* ] を選択し、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" [グループの種類の選択] セクション" lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. グループに名前と説明を付けて、[次へ] をクリックします。

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="[基本の設定] セクション" lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

## <a name="step-2-configure-protection"></a>手順 2: 保護を構成する

Defender for Office 365の一部の機能は既定で構成され、有効になっていますが、セキュリティ操作では既定の保護レベルを引き上げることが必要な場合があります。

一部の機能 *はまだ構成されていません* 。 保護を構成するには、次の 3 つのオプションがあります。

- **事前設定されたセキュリティ ポリシーを自動的に割り当てます**。[事前設定されたセキュリティ ポリシー](../office-365-security/preset-security-policies.md) は、すべての機能にわたって一様なレベルの保護をすばやく割り当てる方法として提供されます。 **_standard_*_ または _*_strict_** から選択できます。 適切な方法は、事前設定されたセキュリティ ポリシーから始めてから、機能と独自の脅威環境の詳細を学習するときにポリシーを微調整することです。 ここでの利点は、ユーザーのグループをできるだけ早く保護し、後で保護を調整できることです。 (この方法をお勧めします。)
- **ベースライン保護を手動で構成** する - 環境を自分で構成する場合は、「[脅威から](../office-365-security/protect-against-threats.md)保護する」のガイダンスに従って、保護の *ベースライン* をすばやく実現できます。 この方法を使用すると、構成可能な設定の詳細を確認できます。 また、後でポリシーを微調整することもできます。
- ***カスタム* 保護ポリシーを構成** する - 評価の一環として、カスタム保護ポリシーを構築して割り当てることもできます。 ポリシーのカスタマイズを開始する前に、これらの保護ポリシーが適用および適用される優先順位を理解しておくことが重要です。 セキュリティ操作では、安全なリンクと安全な添付ファイルのセキュリティ ポリシーを定義するために、プリセットが適用されている場合でも、特定のポリシーを作成する必要があります。
> [!IMPORTANT]
> **カスタム保護ポリシーを構成する必要がある場合** は、**Standard** と **Strict** のセキュリティ定義を構成する値を調べる必要があります。*[EOP とMicrosoft Defender for Office 365セキュリティの推奨設定](../office-365-security/recommended-settings-for-eop-and-office365.md)* です。 構成が行われる前に表示される既定値も一覧表示されます。 カスタム ビルドが逸脱する場所のスプレッドシートを保持します。

### <a name="assign-preset-security-policies"></a>事前設定されたセキュリティ ポリシーを割り当てる

MDO を評価する場合は *、推奨されるベースライン ポリシー* から始めてから、評価期間の過程で必要に応じてそれらを調整することをお勧めします。

推奨される EOP とDefender for Office 365保護ポリシーを迅速に有効にし、評価の一環として特定のパイロット ユーザーまたは定義されたグループに割り当てることができます。 事前設定されたポリシーは、基準 **標準** 保護テンプレートまたはより積極的な **Strict** 保護テンプレートを提供します。このテンプレートは、個別に割り当てたり、組み合わせたりすることができます。

[EOP の事前設定済みセキュリティ ポリシーと、手順の概要を説明するMicrosoft Defender for Office 365](../office-365-security/preset-security-policies.md)記事を次に示します。

1. Microsoft 365 テナントにログオンします。 Microsoft 365 Defender ポータルへのアクセス権を持つアカウント、Office 365の組織管理ロールに追加されたアカウント、または Microsoft 365 のセキュリティ管理者ロールを使用します。
2. ナビゲーション メニューの [電子メール & コラボレーション] で *[ポリシー&ルール* ] を選択します。

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text=" クリックする [ポリシー&ルール] メニュー項目" lightbox="../../media/mdo-eval/5_mdo-eval-pilot-policies.png":::

3. [ポリシー & ルール] ダッシュボードで、[ *脅威ポリシー*] をクリックします。

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text=" クリックする [脅威ポリシー] メニュー項目" lightbox="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png":::

4. Microsoft 365 Defender ポータルで、ナビゲーション メニューから [脅威の管理] を展開し、サブメニューから [ポリシー] を選択します。
5. ポリシー ダッシュボードで、[ *事前設定されたセキュリティ ポリシー*] をクリックします。

   :::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="脅威ポリシーの種類" lightbox="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png":::

6. [ *編集] を* クリックして、Standard ポリシーまたは Strict ポリシーを構成して割り当てます。

   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="[プリセット セキュリティ ポリシー] ページの各種ポリシーに適用されるさまざまな設定" lightbox="../../media/mdo-eval/8-mdo-eval-pilot-preset.png":::

7. 必要に応じて、ベースライン ***EOP** _ 保護を特定のパイロット ユーザーまたはユーザー グループに適用する条件を追加し、_Next* を選択して続行します。

   たとえば、パイロット評価のDefender for Office 365条件は、受信者が定義済 *みの Defender for Office 365 Standard Protection* グループの *メンバー* であり、そのグループにアカウントを追加するか、グループからアカウントを削除することによって管理される場合に適用できます。

   :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="EOP 保護と見なされるポリシー" lightbox="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png":::

8. 必要に応じて、ベースライン ***MDO** _ 保護を特定のパイロット ユーザーまたはユーザー グループに適用する条件を追加します。 _Next* をクリックして続行します。

   たとえば、受信者が定義済みの *Standard Protection* グループの *メンバー* である場合、パイロット評価のDefender for Office 365条件Defender for Office 365適用し、グループ経由でアカウントを追加/削除して管理できます。

   :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="Office 365保護の防御と見なされるポリシー" lightbox="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png":::

9. 事前設定されたセキュリティ ポリシーを割り当てるための変更を確認して確認します。
10. 事前設定された保護ポリシーは、Microsoft 365 Defender ポータル > ポリシー&ルール>脅威ポリシー>に戻り、[*プリセット セキュリティ ポリシー*] タイルをクリックすることで管理 (再構成、再適用、無効など) できます。

### <a name="configure-custom-protection-policies"></a>カスタム保護ポリシーを構成する

定義済みの *Standard* または *Strict* Defender for Office 365 ポリシー テンプレートを使用すると、パイロット ユーザーに推奨されるベースライン保護が提供されます。 ただし、評価の一環としてカスタム保護ポリシーを構築して割り当てることもできます。

[電子メール保護の順序と優先順位](../office-365-security/how-policies-and-protections-are-combined.md)Office 365説明するように、適用および適用時にこれらの保護ポリシーが取る優先順位に注意することが *重要* です。

次の表に、カスタム保護ポリシーの構成と割り当てに関する参照とガイダンスを示します。

<br>

****

|ポリシー|説明|参照|
|:---:|---|---|
|接続フィルター|IP アドレスを使用して、適切または不適切な送信元電子メール サーバーを特定します。|[EOP で既定の接続フィルター ポリシーを構成する](../office-365-security/configure-the-connection-filter-policy.md)|
|マルウェア対策|実行するアクションやマルウェアが検出された場合に通知するユーザーなど、電子メール マルウェアからユーザーを保護します。|[EOP のマルウェア対策ポリシーを構成する](../office-365-security/configure-anti-malware-policies.md)|
|スプーフィング対策|スプーフィング インテリジェンスとスプーフィング インテリジェンス分析情報を使用して、スプーフィングの試行からユーザーを保護します。|[Defender for Office 365でスプーフィング インテリジェンスを構成する](../office-365-security/learn-about-spoof-intelligence.md)|
|スパム対策|スパムが検出された場合に実行するアクションなど、電子メールスパムからユーザーを保護します。|[Defender for Office 365でスパム対策ポリシーを構成する](../office-365-security/configure-your-spam-filter-policies.md)|
|フィッシング対策|フィッシング攻撃からユーザーを保護し、疑わしいメッセージに関する安全に関するヒントを構成する|[詳細については、「Microsoft Defender for Office 365 のフィッシング詐欺対策ポリシーを構成する」を参照してください。](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|安全な添付ファイル|SharePoint、OneDrive、Teams の電子メールの添付ファイルとファイル内の悪意のあるコンテンツからユーザーを保護します。|[Defender for Office 365で安全な添付ファイル ポリシーを設定する](../office-365-security/set-up-safe-attachments-policies.md)|
|安全なリンク|電子メール メッセージまたは Office デスクトップ アプリで悪意のあるリンクを開いたり共有したりできないようにユーザーを保護します。|[Defender for Office 365で安全なリンク ポリシーを設定する](../office-365-security/set-up-safe-links-policies.md)|
|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>手順 3: 機能を試し、シミュレーション、監視、メトリックについて理解する

パイロットのセットアップと構成が完了したので、Microsoft Defender for Microsoft 365 に固有のレポート、監視、攻撃シミュレーション ツールについて理解しておくことが役に立ちます。

<br>

****

|機能|説明|詳細情報|
|---|---|---|
|脅威エクスプローラー|脅威エクスプローラーは、セキュリティ運用チームが脅威を調査して対応し、Office 365内のメールやファイルのマルウェアやフィッシングの疑いに関する情報だけでなく、組織に対するその他のセキュリティ上の脅威やリスクに関する情報を表示するのに役立つ強力なリアルタイムツールです。|[脅威エクスプローラーとリアルタイムの検出のビュー](../office-365-security/threat-explorer-views.md)|
|攻撃シミュレーター|Microsoft 365 Defender ポータルで攻撃シミュレーション トレーニングを使用すると、組織内で現実的な攻撃シナリオを実行できます。これにより、実際の攻撃が環境に影響を与える前に脆弱なユーザーを特定して見つけることができます。|[攻撃シミュレーション トレーニングの使用を開始する](../office-365-security/attack-simulation-training-get-started.md)|
|レポート ダッシュボード|左側のナビゲーション メニューで [レポート] をクリックし、[電子メール & コラボレーション] 見出しを展開します。 電子メール & コラボレーション レポートは、セキュリティ傾向を特定することです。その一部では、アクション ([送信に移動] などのボタンを使用)、メールフローの状態の概要、トップ マルウェア、スプーフィング検出、侵害されたユーザー、メール待ち時間、安全なリンク、安全な添付ファイルレポートなどの傾向を示す他のレポートを実行できます。 これらのメトリックは自動的に生成されます。|[レポートの表示](../office-365-security/view-email-security-reports.md)|
|

## <a name="next-steps"></a>次の手順

[Microsoft Defender for Endpoint の評価](eval-defender-endpoint-overview.md)

[Microsoft Defender for Office 365の評価](eval-defender-office-365-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る

---
title: Microsoft Defender for Office 365 Defender Microsoft 365
description: セキュリティ/コンプライアンス センターから Office 365 Defender への変更Microsoft 365します。
keywords: Microsoft 365セキュリティ、 Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、単一ウィンドウのガラス、新しいセキュリティ ポータル、新しい Defender セキュリティ ポータルの開始
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: 95471f444117e1a44abe8de76c95cda52d5f7930
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842605"
---
# <a name="microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft Defender for Office 365 Defender Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>クイック リファレンス

次の図と表に、コンプライアンス センターと Defender の Office 365 セキュリティ &ナビゲーションMicrosoft 365示します。

> [!div class="mx-imgBorder"]
> ![移動先のイメージ](../../media/mdo-m3d-security-center.png)

<br>

****

|Office 365 セキュリティ/コンプライアンス|Microsoft 365 Defender|Microsoft 365 コンプライアンス センター|Exchange 管理センター|
|---|---|---|---|
|アラート|メールと共同作業|||
|分類||コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)||
|データ損失防止||コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)||
|レコード管理||コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage) ||
|情報ガバナンス||コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)||
|脅威の管理|メールと共同作業|||
|メール フロー|||「[管理Exchange」を参照してください。](https://admin.exchange.microsoft.com/#/)|
|データのプライバシー||コンプライアンス[センター Microsoft 365する](https://compliance.microsoft.com/homepage)||
|検索|検索|||
|レポート|レポート|||
|サービス アシュアランス|設定|||
|

[Microsoft 365 Defender](./overview-security-center.md)は、既存の Microsoft セキュリティ ポータルのセキュリティ機能 (Microsoft Defender セキュリティ センター とコンプライアンス センター Office 365 <https://security.microsoft.com> を&します。 この強化されたセンターは、セキュリティ チームが脅威から組織を効果的かつ効率的に保護するのに役立ちます。

Office 365 セキュリティとコンプライアンス ポータル (protection.office.com) に精通している場合は、Microsoft 365 Defender の変更点と改善点について説明します。

メリットの詳細: Defender の概要[Microsoft 365する](overview-security-center.md)

コンプライアンス関連のアイテムをお探しの場合は、「[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/homepage)」へお越しください。

## <a name="whats-changed"></a>変更内容

この表は、 **セキュリティ/コンプライアンス センター** と **Microsoft 365 セキュリティ** ポータルの間で変更が発生したメールと共同作業の領域のクイック リファレンスです。 これらの領域の詳細については、リンクをクリックしてください。

<br>

****

|分野|変更の説明|
|---|---|
|[[メール エンティティ] ページ](../office-365-security/mdo-email-entity-page.md)|このページは、今まで色々なページやビューに分散していたメール情報を **統合** します。 脅威と傾向に関するメールの調査結果は、*1 か所に集中しています*。 ヘッダー情報とメールプレビューは、他の便利なメール関連情報と共に同じメール ページからアクセスできます。 同様に、悪意のある添付ファイルまたは URL に対するデトネーションの状態は、同じページのタブにあります。 [メール エンティティ] ページは、管理者やセキュリティ運用チームがメールの脅威とその状態をすばやく把握し、処理を迅速に決定するのに役立ちます。|
|[調査](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-security-center)|[Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) および[Defender for Endpoint](../defender-endpoint/automated-investigations.md)の AIR 機能を 1 つにまとめます。 これらの更新プログラムと改善により、セキュリティ運用チームは、メール、共同作業のコンテンツ、ユーザー アカウント、デバイスに対する自動調査と修復処理に関する詳細を 1 か所で確認できます。|
|[通知ビュー](../../compliance/alert-policies.md)|[**セキュリティとコンプライアンス]** センターの [通知の表示] Officeウィンドウに、Defender へのリンクがMicrosoft 365されています。 [アラート ページを開 **く] リンクをクリック** し、Defender Microsoft 365開きます。 通知キュー内の Office 365 をクリックすると、**[通知の表示]** ページにアクセスできます。|
|[攻撃シミュレーション トレーニング](../office-365-security/attack-simulation-training-insights.md)|攻撃シミュレーション トレーニングを使用して、組織内で現実的な攻撃シナリオを実行します。 これらのシミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、従業員をトレーニングするのに役立ちます。 攻撃シミュレーション トレーニングには、より多くのオプション、強化されたレポート、および強化されたトレーニング フローおよび配信と管理がより容易になったトレーニングシナリオが含まれています。|
|

次の領域に変更はありません。

- [Explorer](../office-365-security/threat-explorer.md)
- [ポリシーとルール](../../compliance/alert-policies.md)
- [キャンペーン](../office-365-security/campaigns.md)
- [Submissions](../office-365-security/admin-submission.md)
- [確認](./m365d-action-center.md)
- [脅威トラッカー](../office-365-security/threat-trackers.md)

また、この記事の下にある **関連情報** セクションを確認します。

> [!IMPORTANT]
> [Microsoft 365 セキュリティ ポータル ( <https://security.microsoft.com> ) は、 および でセキュリティ機能 <https://securitycenter.windows.com> を組み合わせたものになります <https://protection.office.com> 。 ただし、表示される内容はサブスクリプションによって異なります。 たとえば、Microsoft Defender for Office 365 Plan 1 または 2 をスタンドアロン サブスクリプションとしてお持ちの場合、Security for Endpoints 関連の機能は表示されません。また Defender for Office Plan 1 のお客様の場合、Threat Analytics などのアイテムは表示されません。

> [!TIP]
> EOP Exchange Online Protection (EOP) 関数はすべて、Microsoft 365 Defender の主要な要素Office 365。

## <a name="microsoft-365-defender-home-page"></a>Microsoft 365Defender のホーム ページ

ポータルのホーム ページには次が表示されます。

- セキュリティ スコアの評価
- リスクに晒されているユーザーとデバイスの数
- アクティブなインシデント キュー
- 特権 OAuth アプリの一覧
- デバイス正常性データ
- Microsoft のセキュリティ インテリジェンスの Twitter フィードからのツイート
- その他のサマリー情報

**ガイド 付 ツアー** を使用して、エンドポイントまたはメールと共同作業のページのクイック ツアーを見ることができます。 ここに表示される内容は、ライセンスが、Defender for Office 365、 Defender for Endpoint のどちらか、または両方をお持ちの場合によって異なる点に注意してください。

**Office 365 セキュリティ/コンプライアンス センター** のリンクも異なります。 最後のリンクは、最近の更新プログラムを表示する **[新機能]** ページへのリンクです。

## <a name="improved-capabilities"></a>強化された機能

左側のナビゲーションまたはクイック起動バーは見慣れたものに見えます。 ただし、このセキュリティ センターには、いくつかの新しい要素や更新された要素があります。

### <a name="incidents-and-alerts"></a>インシデントと警告

メール、デバイス、ID 全体でインシデントと通知の管理を 1 か所で行います。 現在、警告が [調査] ノードの下に表示されており、攻撃のより広範なビューを提供しています。 警告ページには、攻撃シグナルを組み合わせて詳細なストーリーを構築することで、アラートの完全なコンテキストが提供されます。 以前は、アラートはさまざまなワークロードに特有のものでした。 新しく統合されたエクスペリエンスにより、さまざまなワークロード全体で一貫した警告が表示されます。 トリアージ、調査、効果的なアクションをすばやく実行できます。

- [調査の詳細](incidents-overview.md)
- [通知の管理に関するその他の情報](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![通知とアクションのクイック起動バー](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>検索

エンドポイント、Office 365 メールボックスなどに対する脅威、マルウェア、悪意のあるアクティビティを積極的に検索するために、[高度な検索クエリ](advanced-hunting-overview.md)を使用します。 これらの強力なクエリを使用して、既知の脅威と潜在的な脅威の両方を示す脅威インジケーターとエンティティを見つけて確認できます。

[カスタム検出ルール](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) は、高度な検索クエリから作成できます。侵害アクティビティや間違った構成のデバイスを示すイベントを積極的に監視することができます。

### <a name="action-center"></a>アクション センター

アクション センターには、自動調査と自動応答機能によって作成された調査が表示されます。 この Microsoft 365 Defender の自動自己修復機能は、特定のイベントに自動的に応答することでセキュリティ チームを支援します。

[アクション センターの詳細](m365d-action-center.md)

#### <a name="threat-analytics"></a>脅威の分析

専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。 脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。 脅威の分析には以下が含まれます。

- Microsoft Defender for Office 365 からのメール関連の検出と移行。 これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。
- 脅威に関連するインシデントが表示されます。
- レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。
脅威分析には、Microsoft 365 Defender の左上のナビゲーション バーから、または組織の上位の脅威を示す専用のダッシュボード カードからアクセスできます。

[[脅威の分析を使用して、新たな脅威を追跡し対応する]](./threat-analytics.md)の詳細説明

### <a name="email--collaboration"></a>メールと共同作業

ユーザーのメールへの脅威を追跡および調査し、キャンペーンなどを追跡します。 Office 365 セキュリティ/コンプライアンス センターをご利用の場合は、使い慣れたものになっています。

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Defender の左側にある& (または MSDO) の [電子メール] Microsoft 365メニュー。":::

### <a name="access-and-reports"></a>アクセスとレポート

レポートの表示、設定の変更、およびユーザーの役割変更を行います。

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="セキュリティ センターの左側にあるMicrosoft 365 Defender のアクセス許可とレポートのサイド リンク バー メニュー。":::

> [!NOTE]
> Office 365 ユーザー向け Defender では、Microsoft 365  Defender を使用して DomainKeys 識別メール (DKIM) キーを管理および回転したり、ポリシー & ルールの脅威ポリシー <https://security.microsoft.com/threatpolicy>  \>  \> **DKIM** に移動したりできます。

## <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の高度な検出の例

高度な検出を使用してメールの脅威の検索を開始しますか? 実行する操作:

[Microsoft Defender for Office 365の記事](/microsoft-365/security/office-365-security/defender-for-office-365)の「[使用を開始する](/microsoft-365/security/office-365-security/defender-for-office-365.md#getting-started)」セクションには、次のような論理的な早期構成用の単位があります。

1. 名前に 'Anti' を含むすべてを構成します。
   - マルウェア対策
   - フィッシング対策
   - スパム対策
2. 名前に 'セーフ' を含むすべてを設定します。
   - 安全なリンク
   - 安全な添付ファイル
3. ワークロードを保護する (例: SharePointオンライン、OneDrive、およびTeams)。
4. 0 時間自動削除で保護します。

[リンク](../office-365-security/protect-against-threats.md)をクリックすると、一気にジャンプして、第 1 日目から使用できる構成を入手できます。

**開始** の最後の手順は、**ゼロアワー自動消去**(ZAP) によるユーザー保護です。 ZAP で不審なメールや悪意のあるメール、配信後のメールの自動消去が成功したどうかを知るのはとても重要です。

問題を探し出す場合に、Kusto クエリ言語にすばやく移動できることは、2 つのセキュリティ センターを集約する利点です。 セキュリティ チームは、次の手順を実行して、ZAP ミスを監視 [](https://security.microsoft.com/advanced-hunting) \> **できます**。

1. [高度な検出] ページで [クエリ] をクリックします。
1. 次のクエリを[クエリ] ウィンドウにコピーします。
1. [クエリの実行] を選択します。

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="クエリ パネルの上部で [クエリ] を選択し、過去 7 日間の ZAP アクションをキャプチャするために Kusto クエリを実行した [高度な検索] ページ ([ハンティング] の下)。":::

このクエリのデータは、クエリ自体の下の結果パネルに表示されます。 結果には、カスタマイズ可能な結果セットに 'DeviceName', 'AccountDisplayName'、および 'ZapTime' が含まれています。 ユーザーの記録用に、結果をエクスポートすることもできます。 クエリがもう一度必要な場合は、**[保存する]** > **[以下の名前で保存する]** の順に選択し、クエリ、共有クエリ、またはコミュニティ クエリの一覧にそのクエリを追加します。

## <a name="related-information"></a>関連情報

- [Microsoft Defender for Office 365 Defender Microsoft 365](microsoft-365-security-center-mdo.md)
- [アクション センター](./m365d-action-center.md)
- [メールと共同作業の通知](../../compliance/alert-policies.md#default-alert-policies)
- [デバイス、メール、アプリ、ID 全体の脅威を探す](./advanced-hunting-query-emails-devices.md)
- [カスタム検出ルール](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [フィッシング攻撃のシミュレーションを作成](../office-365-security/attack-simulation-training.md)して[従業員をトレーニングするためのペイロードを作成する](../office-365-security/attack-simulation-training-payloads.md)

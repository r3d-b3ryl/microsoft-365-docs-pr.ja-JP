---
title: Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365
description: Office 365 セキュリティ/コンプライアンス センターから Microsoft 365 セキュリティ センターへの変更について説明します。
keywords: Microsoft 365 のセキュリティ、Microsoft 365 セキュリティ センターの使用を開始する、OATP、MDATP、MDO、MDE、ガラスの単一ウィンドウ、新しいセキュリティ ポータル、新しい Defender セキュリティ ポータル
ms.date: 02/02/2021
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
ms.openlocfilehash: a31927c11d2cfdf808abff1aeb02879ca3e84130
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906831"
---
# <a name="microsoft-defender-for-office-365-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**
- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Office 365](../office-365-security/office-365-atp.md)

[https://security.microsoft.com](https://security.microsoft.com) で強化された[Microsoft 365 セキュリティ センター](./overview-security-center.md) は、Microsoft Defender セキュリティ センターや Office 365 セキュリティ/コンプライアンス センターなどの既存の Microsoft セキュリティ ポータルのセキュリティ機能を組み合わせた製品です。 この強化されたセンターは、セキュリティ チームが脅威から組織を効果的かつ効率的に保護するのに役立ちます。

この記事では、Office 365 セキュリティ/コンプライアンス ポータル (protection.office.com) を使い慣れたユーザーに、Microsoft 365 セキュリティ センターで行った変更と改善点について説明します。

利点の詳細説明: [Microsoft 365 セキュリティ センターの概要](overview-security-center.md)

コンプライアンス関連のアイテムをお探しの場合は、「[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/homepage)」へお越しください。

## <a name="whats-changed"></a>変更内容

この表は、 **セキュリティ/コンプライアンス センター** と **Microsoft 365 セキュリティ** ポータルの間で変更が発生したメールと共同作業の領域のクイック リファレンスです。 これらの領域の詳細については、リンクをクリックしてください。

|**領域**  |**変更の説明**  |
|---------|---------|
| [[メール エンティティ] ページ](../office-365-security/mdo-email-entity-page.md) | このページは、今まで色々なページやビューに分散していたメール情報を **統合** します。 脅威と傾向に関するメールの調査結果は、*1 か所に集中しています*。 ヘッダー情報とメールプレビューは、他の便利なメール関連情報と共に同じメール ページからアクセスできます。 同様に、悪意のある添付ファイルまたは URL に対するデトネーションの状態は、同じページのタブにあります。 [メール エンティティ] ページは、管理者やセキュリティ運用チームがメールの脅威とその状態をすばやく把握し、処理を迅速に決定するのに役立ちます。  |
| [調査](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-security-center) | [Defender for Office 365](../office-365-security/office-365-atp.md) および[Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)の AIR 機能を 1 つにまとめます。 これらの更新プログラムと改善により、セキュリティ運用チームは、メール、共同作業のコンテンツ、ユーザー アカウント、デバイスに対する自動調査と修復処理に関する詳細を 1 か所で確認できます。  | 
| [通知ビュー](../../compliance/alert-policies.md) | Office Security and Compliance センターの **[通知の表示]** ウィンドウに、Microsoft 365 セキュリティ センターへのリンクがあります。 **[通知のページを開く]** のリンクをクリックすると、 Microsoft 365 セキュリティ センターが表示されます。 通知キュー内の Office 365 をクリックすると、**[通知の表示]** ページにアクセスできます。 |
| [攻撃シミュレーション トレーニング](../office-365-security/attack-simulation-training-insights.md)   | 攻撃シミュレーション トレーニングを使用して、組織内で現実的な攻撃シナリオを実行します。 これらのシミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、従業員をトレーニングするのに役立ちます。 攻撃シミュレーション トレーニングには、より多くのオプション、強化されたレポート、および強化されたトレーニング フローおよび配信と管理がより容易になったトレーニングシナリオが含まれています。  |

次の領域に変更はありません。
- [Explorer](../office-365-security/threat-explorer.md)
- [ポリシーとルール](../../compliance/alert-policies.md)
- [キャンペーン](../office-365-security/campaigns.md)
- [Submissions](../office-365-security/admin-submission.md)
- [確認](./mtp-action-center.md)
- [脅威トラッカー](../office-365-security/threat-trackers.md)

また、この記事の下にある **関連情報** セクションを確認します。

> [!IMPORTANT]
> Microsoft 365 セキュリティ ポータル (https://security.microsoft.com) は、https://securitycenter.windows.comとhttps://protection.office.comにあるキュリティ機能を組合わせています。 ただし、表示される内容はサブスクリプションによって異なります。 たとえば、Microsoft Defender for Office 365 Plan 1 または 2 をスタンドアロン サブスクリプションとしてお持ちの場合、Security for Endpoints 関連の機能は表示されません。また Defender for Office Plan 1 のお客様の場合、Threat Analytics などのアイテムは表示されません。

## <a name="microsoft-365-security-center-home-page"></a>Microsoft 365 セキュリティ センターのホーム ページ

ポータルのホーム ページには次が表示されます。

- セキュリティ スコアの評価
- リスクに晒されているユーザーとデバイスの数
- アクティブなインシデントの一覧
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

[アクション センターの詳細](mtp-action-center.md)

#### <a name="threat-analytics"></a>脅威の分析
専門家の Microsoft セキュリティ調査員から脅威インテリジェンスを取得します。 脅威の分析は、新たな脅威に直面している場合に、セキュリティ チームの効率を向上するのに役立ちます。 脅威の分析には以下が含まれます。

- Microsoft Defender for Office 365 からのメール関連の検出と移行。 これは、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて表示されます。
- 脅威に関連するインシデントが表示されます。 
- レポート内のアクション可能な情報をすばやく認識して使用するための強化されたエクスペリエンス。 脅威の分析には、Microsoft 365 セキュリティ センターの左上のナビゲーション バーからか、組織の上位の脅威を表示する専用のダッシュボード カードからアクセスできます。 

[[脅威の分析を使用して、新たな脅威を追跡し対応する]](./threat-analytics.md)の詳細説明

### <a name="email--collaboration"></a>メールと共同作業

ユーザーのメールへの脅威を追跡および調査し、キャンペーンなどを追跡します。 Office 365 セキュリティ/コンプライアンス センターをご利用の場合は、使い慣れたものになっています。

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Microsoft 365 セキュリティ センターの左側にある [メールと共同作業] (または MSDO) のクイック起動メニュー。":::

### <a name="access-and-reports"></a>アクセスとレポート

レポートの表示、設定の変更、およびユーザーの役割変更を行います。

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="セキュリティ センターの左側にある、Microsoft 365 セキュリティ センターのアクセス許可とレポートのクイック起動メニュー。":::


> [!NOTE]
> Defender for Office 365 ユーザーの場合、Microsoft 365 セキュリティ センター (https://security.microsoft.com/threatpolicy) を通じて DomainKeys Identified Mail (DKIM) キーを *管理および回転* したり、**[ポリシーとルール] > [脅威ポリシー] > [DKIM]** の順に移動したりすることができます。

## <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の高度な検出の例
高度な検出を使用してメールの脅威の検索を開始しますか? 実行する操作:

[Microsoft Defender for Office 365の記事](../office-365-security/office-365-atp.md)の「[使用を開始する](../office-365-security/office-365-atp.md#getting-started)」セクションには、次のような論理的な早期構成用の単位があります。

1. 名前に "anti (対策)" を使用してすべてを構成します。
- マルウェア対策
- フィッシング詐欺対策
- スパム対策
2. 名前に "安全" を使用してすべてを設定します。
- 安全なリンク
- 安全な添付ファイル
3. ワークロードを保護する (例: OSharePoint Online、OneDrive と Teams)
4. ゼロアワー自動消去を使用して保護する

[リンク](../office-365-security/protect-against-threats.md)をクリックすると、一気にジャンプして、第 1 日目から使用できる構成を入手できます。

**開始** の最後の手順は、**ゼロアワー自動消去**(ZAP) によるユーザー保護です。 ZAP で不審なメールや悪意のあるメール、配信後のメールの自動消去が成功したどうかを知るのはとても重要です。

問題を探し出す場合に、Kusto クエリ言語にすばやく移動できることは、2 つのセキュリティ センターを集約する利点です。 セキュリティ チームは、次の手順を実行して、ZAPにミスがないかどうかを **[検出]** > **[高度な検出]** の下にある[[ここ]](https://security.microsoft.com/advanced-hunting)で、検出できます。

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

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="[クエリ] パネルの上部で [クエリ] が選択された状態で [高度な検出] ページ ([検出] の下) で、過去 7 日間の ZAP アクションをキャプチャするために、Kusto クエリを実行中。":::

このクエリのデータは、クエリ自体の下の結果パネルに表示されます。 結果には、カスタマイズ可能な結果セットに 'DeviceName', 'AccountDisplayName'、および 'ZapTime' が含まれています。 ユーザーの記録用に、結果をエクスポートすることもできます。 クエリがもう一度必要な場合は、**[保存する]** > **[以下の名前で保存する]** の順に選択し、クエリ、共有クエリ、またはコミュニティ クエリの一覧にそのクエリを追加します。

## <a name="related-information"></a>関連情報
- [Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [アクション センター](./mtp-action-center.md)
- [メールと共同作業の通知](../../compliance/alert-policies.md#default-alert-policies)
- [デバイス、メール、アプリ、ID 全体の脅威を探す](./advanced-hunting-query-emails-devices.md)
- [カスタム検出ルール](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules)
- [フィッシング攻撃のシミュレーションを作成](../office-365-security/attack-simulation-training.md)して[従業員をトレーニングするためのペイロードを作成する](../office-365-security/attack-simulation-training-payloads.md)
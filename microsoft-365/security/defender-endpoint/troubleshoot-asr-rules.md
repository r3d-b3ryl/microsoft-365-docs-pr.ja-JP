---
title: MICROSOFT DEFENDER FOR ENDPOINT ASR ルールのレポートとトラブルシューティング
description: このトピックでは、MICROSOFT DEFENDER FOR ENDPOINT ASR ルールを報告してトラブルシューティングする方法について説明します
keywords: 攻撃面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、アンチエクスプロイト、アンチエクスプロイト、エクスプロイト、感染防止、Microsoft Defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: b1a90ec887f62a3c486c30ed50b87482de451c01
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471013"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-endpoint-asr-rules"></a>MICROSOFT DEFENDER FOR ENDPOINT ASR ルールのレポートとトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>は、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するための新しいインターフェイスです。 ここでは組織のセキュリティの健全性を簡単に表示したり、デバイス、ユーザー、アプリを構成したり、不審なアクティビティのアラートを取得したりできます。 Microsoft 365 Defender ポータルは、セキュリティ管理者とセキュリティ運用チームが組織の管理と保護を強化することを目的としています。 Microsoft 365 Defender ポータルに<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>アクセスします。

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>では、資産内の現在の ASR ルールの構成とイベントを完全に確認できます。 これらのレポートを設定するには、デバイスをMicrosoft Defender for Endpoint サービスにオンボードする必要があることに注意してください。
Microsoft 365 Defender ポータルのスクリーンショットを次に示します (**[Reports** Devices Attack surface reduction]\(レポート \> **デバイス** \> **の攻撃の軽減**\) の下にあります。 デバイス レベルで、[**攻撃面の縮小ルール**] ウィンドウで **[構成**] を選択します。 次の画面が表示され、特定のデバイスを選択し、個々の ASR ルールの構成を確認できます。

:::image type="content" source="images/asrrulesnew.png" alt-text="[ASR 規則] ページ" lightbox="images/asrrulesnew.png":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>Microsoft Defender for Endpoint - 高度なハンティング

Microsoft Defender for Endpointの最も強力な機能の 1 つは、高度な捜索です。 高度な捜索に慣れていない場合は、高度な捜索 [で脅威をプロアクティブに検索](advanced-hunting-overview.md)する方法を参照してください。

高度なハンティングは、Defender for Endpoint がデバイスから収集する、キャプチャされた (未加工) データの最大 30 日間を探索できる、クエリベースの (Kusto 照会言語) 脅威検出ツールです。 高度な捜索を通じて、イベントを事前に調べて、興味深いインジケーターとエンティティを見つけることができます。 データへの柔軟なアクセスは、既知の脅威と潜在的な脅威の両方に対する制約のない捜索に役立ちます。

高度な捜索を通じて、ASR ルール情報を抽出し、レポートを作成し、特定の ASR ルール監査またはブロック イベントのコンテキストに関する詳細な情報を取得できます。

ASR ルール イベントは、Microsoft 365 Defenderの高度なハンティング セクションの DeviceEvents テーブルからクエリを実行できます。 たとえば、次のような単純なクエリでは、過去 30 日間のデータ ソースとして ASR ルールを持つすべてのイベントを報告でき、ActionType カウントで集計されます。この場合は ASR ルールの実際のコード名になります。

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高度なハンティング クエリ" lightbox="images/adv-hunt-querynew.png":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="高度なハンティング ページ" lightbox="images/adv-hunt-sc-2new.png":::

高度なハンティングを使用すると、個々のマシンで何かを特定するか、環境全体から分析情報を抽出するかに関係なく、何が起こっているかを確認できるように、クエリを好みに合わせて整形できます。

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Microsoft Defender for Endpointマシンのタイムライン

高度な捜索の代わりに、スコープが狭いマシンタイムラインMicrosoft Defender for Endpoint。 デバイスの収集されたすべてのイベントを過去 6 か月間、Microsoft 365 Defenderで表示するには、[コンピューター] ボックスの一覧に移動し、特定のコンピューターを選択し、[タイムライン] タブをクリックします。

次の図は、特定のエンドポイント上のこれらのイベントのタイムライン ビューのスクリーンショットです。 このビューから、右側のウィンドウに沿って任意のイベント グループに基づいてイベントリストをフィルター処理できます。 アラートを表示し、履歴タイムラインをスクロールしながら、フラグ付きイベントと詳細イベントを有効または無効にすることもできます。

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Microsoft 365 Defenderタイムライン" lightbox="images/mic-sec-def-timelinenew.png":::

## <a name="how-to-troubleshoot-asr-rules"></a>ASR ルールのトラブルシューティング方法

最初の最も直接的な方法は、powerShell コマンドレットを使用して ASR 規則が有効になっている (およびその構成) Windows デバイスでローカルで確認することです。

ASR ルールの影響と操作をトラブルシューティングするためにWindows提供するその他のいくつかの情報源を次に示します。

### <a name="querying-which-rules-are-active"></a>アクティブなルールのクエリ

ASR 規則が既に有効になっているかどうかを判断する最も簡単な方法の 1 つは、PowerShell コマンドレット Get-MpPreference を使用することです。

次に例を示します。

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference スクリプトを取得する" lightbox="images/getmpreferencescriptnew.png":::

複数の ASR ルールがアクティブであり、さまざまなアクションが構成されています。

ASR 規則に関する上記の情報を展開するには、 **AttackSurfaceReductionRules_Ids** プロパティや **AttackSurfaceReductionRules_Actions** プロパティを使用します。

例:

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference の取得の例" lightbox="images/getmpref-examplenew.png":::

上記は、0 (未構成) とは異なる設定を持つ ASR ルールのすべての ID を示しています。

次の手順では、各ルールが構成されている実際のアクション (ブロックまたは監査) を一覧表示します。

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="mppreference の取得の例 2" lightbox="images/getmpref-example2new.png":::

### <a name="querying-blocking-and-auditing-events"></a>ブロック イベントと監査イベントのクエリ

ASR ルール イベントは、Windows Defender ログ内で表示できます。

それにアクセスするには、Windows イベント ビューアーを開き、**アプリケーションとサービス ログ** \> **Microsoft** \> **Windows Windows Defender** \>  \> **Operational** に移動します。

:::image type="content" source="images/eventviewerscrnew.png" alt-text="イベント ビューアー ページ" lightbox="images/eventviewerscrnew.png":::

## <a name="microsoft-defender-antimalware-protection-logs"></a>Microsoft Defender マルウェア対策保護ログ

また、必要に応じてタスクを管理および構成し、自動化するために使用できる、`*mpcmdrun.exe*`Microsoft Defender ウイルス対策専用のコマンド ライン ツールを使用してルール イベントを表示することもできます。

このユーティリティは *、%ProgramFiles%\Windows Defender\MpCmdRun.exe* にあります。 管理者特権のコマンド プロンプト (つまり、管理者として実行) から実行する必要があります。

サポート情報を生成するには、 *-getfilesMpCmdRun.exe入力します*。 しばらくすると、複数のログがアーカイブ (MpSupportFiles.cab) にパッケージ化され、*C:\ProgramData\Microsoft\Windows Defender\Support* で使用できるようになります。

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="マルウェア保護ログ" lightbox="images/malware-prot-logsnew.png":::

そのアーカイブを抽出すると、トラブルシューティングの目的で使用できるファイルが多数あります。

最も関連性の高いファイルは次のとおりです。

- **MPOperationalEvents.txt**: このファイルには、Windows Defenderの操作ログのイベント ビューアーで見つかったのと同じレベルの情報が含まれています。
- **MPRegistry.txt**: このファイルでは、サポート ログがキャプチャされた時点から、現在のすべてのWindows Defender構成を分析できます。
- **MPLog.txt**: このログには、Windows Defenderのすべてのアクション/操作に関する詳細な情報が含まれています。

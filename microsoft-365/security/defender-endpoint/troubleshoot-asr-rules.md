---
title: エンドポイント ASR ルールの Microsoft Defender のレポートとトラブルシューティング
description: このトピックでは、Microsoft Defender for Endpoint ASR ルールを報告およびトラブルシューティングする方法について説明します。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、エンドポイント用 microsoft Defender
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
# <a name="report-and-troubleshoot-microsoft-defender-for-endpoint-asr-rules"></a>エンドポイント ASR ルールの Microsoft Defender のレポートとトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderは</a>、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するための新しいインターフェイスです。 ここでは組織のセキュリティの健全性を簡単に表示したり、デバイス、ユーザー、アプリを構成したり、不審なアクティビティのアラートを取得したりできます。 このMicrosoft 365 Defenderは、セキュリティ管理者とセキュリティ運用チームが組織の管理と保護を強化することを目的としています。 [ポータル] Microsoft 365 Defenderにアクセスします<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>。

この<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderでは</a>、現在の ASR ルールの構成と、資産内のイベントを完全に確認できます。 これらのレポートを設定するには、デバイスを Microsoft Defender for Endpoint サービスにオンボードする必要があります。
[レポート デバイス攻撃の表面縮小] の下Microsoft 365 Defenderポータル \>  \> **のスクリーンショットを次に示します**。 デバイス レベルで、[攻撃表面 **縮小ルール]** ウィンドウ **から [構成] を選択** します。 次の画面が表示され、特定のデバイスを選択し、個々の ASR ルール構成を確認できます。

:::image type="content" source="images/asrrulesnew.png" alt-text="[ASR ルール] ページ" lightbox="images/asrrulesnew.png":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>エンドポイント向け Microsoft Defender - 高度な検索

Microsoft Defender for Endpoint の最も強力な機能の 1 つは、高度な検索です。 高度な狩猟に慣れていない場合は、高度な狩猟で脅威を積極的 [に探す方法を参照してください](advanced-hunting-overview.md)。

高度な検索はクエリ ベース (Kusto Query Language) の脅威検索ツールで、デバイスから Defender for Endpoint が収集するキャプチャされた (生の) データの最大 30 日間を探索できます。 高度な検索を通じて、イベントを積極的に検査して、興味深いインジケーターとエンティティを見つけ出します。 データへの柔軟なアクセスは、既知の脅威と潜在的な脅威の両方に対する抑制されていない検出に役立ちます。

高度な検索を通じて、ASR ルール情報を抽出し、レポートを作成し、特定の ASR ルール監査またはブロック イベントのコンテキストに関する詳細な情報を取得できます。

ASR ルール イベントは、デバイス の詳細な検索セクションの DeviceEvents テーブルからクエリを実行Microsoft 365 Defender。 たとえば、次のような単純なクエリは、過去 30 日間、ASR ルールをデータ ソースとして持つすべてのイベントをレポートし、アクションタイプカウントで集計します。この場合は ASR ルールの実際のコード名になります。

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高度な検索クエリ" lightbox="images/adv-hunt-querynew.png":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="[高度な検索] ページ" lightbox="images/adv-hunt-sc-2new.png":::

高度な検索を使用すると、個別のコンピューターで何かを特定するか、環境全体から分析情報を抽出するかに関係なく、何が起こっているかを確認するために、好みでクエリを形成できます。

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Microsoft Defender for Endpoint machine Timeline

高度な検索に代わる方法ですが、スコープが狭い場合は、Microsoft Defender for Endpoint マシンのタイムラインを使用します。 Microsoft 365 Defender で過去 6 か月間、デバイスのすべての収集イベントを表示するには、[コンピューター] リストに移動し、特定のコンピューターを選択し、[タイムライン] タブをクリックします。

次の図は、特定のエンドポイントでこれらのイベントのタイムライン ビューのスクリーンショットです。 このビューから、右側のウィンドウに沿ったイベント グループに基づいてイベント リストをフィルター処理できます。 アラートを表示したり、履歴タイムラインをスクロールしたりしながら、フラグ付きイベントと詳細イベントを有効または無効にすることもできます。

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="タイムラインMicrosoft 365 Defenderタイムライン" lightbox="images/mic-sec-def-timelinenew.png":::

## <a name="how-to-troubleshoot-asr-rules"></a>ASR ルールのトラブルシューティング方法

最初の最も直接的な方法は、powerShell コマンドレットを使用して、ASR ルールが有効になっている (およびそれらの構成) Windows デバイス上でローカルで確認する方法です。

ASR ルールの影響と運用をトラブルシューティングするために、Windows提供するその他の情報源を次に示します。

### <a name="querying-which-rules-are-active"></a>アクティブなルールのクエリ

ASR ルールが既に有効になっているかどうかを判断する最も簡単な方法の 1 つは、PowerShell コマンドレット Get-MpPreference です。

次に例を示します:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="get mppreference スクリプト" lightbox="images/getmpreferencescriptnew.png":::

複数の ASR ルールがアクティブで、構成されたアクションが異なります。

ASR ルールに関する上記の情報を展開するには、ASR ルールのプロパティAttackSurfaceReductionRules_Idsおよび/**または****AttackSurfaceReductionRules_Actions。**

例:

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference の取得の例" lightbox="images/getmpref-examplenew.png":::

上記は、0 (Not Configured) とは異なる設定を持つ ASR ルールのすべての ID を示しています。

次に、各ルールが構成されている実際のアクション (ブロックまたは監査) を一覧表示します。

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference の例2" lightbox="images/getmpref-example2new.png":::

### <a name="querying-blocking-and-auditing-events"></a>ブロックイベントと監査イベントのクエリ

ASR ルール イベントは、ログ内でWindows Defenderできます。

アクセスするには、イベント ビューアー Windows開\>き、[アプリケーションとサービス ログ] **[Microsoft** \>  \> \> Windows Windows Defender **します**。

:::image type="content" source="images/eventviewerscrnew.png" alt-text="[イベント ビューアー] ページ" lightbox="images/eventviewerscrnew.png":::

## <a name="microsoft-defender-antimalware-protection-logs"></a>Microsoft Defender マルウェア対策保護ログ

また、必要に応じてタスクの管理と構成、`*mpcmdrun.exe*`自動化に使用できる Microsoft Defender ウイルス対策 専用のコマンド ライン ツールを使用してルール イベントを表示することもできます。

このユーティリティは、*%ProgramFiles%\Windows Defender\MpCmdRun.exeにあります*。 管理者特権のコマンド プロンプト (管理者として実行) から実行する必要があります。

サポート情報を生成するには、- *getfilesMpCmdRun.exe入力します*。 しばらくすると、いくつかのログがアーカイブ (MpSupportFiles.cab) にパッケージ化され、*C:\ProgramData\Microsoft\Windows Defender\Support で使用できます*。

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="マルウェア保護ログ" lightbox="images/malware-prot-logsnew.png":::

そのアーカイブを抽出すると、トラブルシューティングの目的で多くのファイルを利用できます。

最も関連性の高いファイルは次のとおりです。

- **MPOperationalEvents.txt**: このファイルには、イベント ビューアーで見つかった、ユーザーの運用ログWindows Defender同じレベルの情報が含まれます。
- **MPRegistry.txt**: このファイルでは、サポート ログがキャプチャされた時点Windows Defender現在の構成を分析できます。
- **MPLog.txt**: このログには、すべてのアクション/操作に関する詳細な情報が含Windows Defender。

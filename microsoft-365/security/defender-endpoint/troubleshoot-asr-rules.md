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
ms.openlocfilehash: fd23f0cdf35a9b7e236a957fed0922192091beb3
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963157"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-endpoint-asr-rules"></a>エンドポイント ASR ルールの Microsoft Defender のレポートとトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

セキュリティ<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365は</a>、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するための新しいインターフェイスです。 ここでは組織のセキュリティの健全性を簡単に表示したり、デバイス、ユーザー、アプリを構成したり、不審なアクティビティのアラートを取得したりできます。 Microsoft 365 セキュリティ センターは、セキュリティ管理者とセキュリティ運用チームが組織をより適切に管理および保護することを目的としています。 で、Microsoft 365セキュリティ センターにアクセスします <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> 。

セキュリティ<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365では</a>、現在の ASR ルールの構成と、資産内のイベントを完全に確認できます。 これらのレポートを設定するには、デバイスを Microsoft Defender for Endpoint サービスにオンボードする必要があります。
セキュリティ センターのスクリーンショットを次に示Microsoft 365レポート デバイス攻撃表面の縮小] \>  \> **の下に示します**。 デバイス レベルで、[攻撃表面 **縮小ルール]** ウィンドウ **から [構成] を選択** します。 次の画面が表示され、特定のデバイスを選択し、個々の ASR ルール構成を確認できます。

:::image type="content" source="images/asrrulesnew.png" lightbox="images/asrrulesnew.png" alt-text="ASR ルール画面。":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>エンドポイント向け Microsoft Defender - 高度な検索

Microsoft Defender for Endpoint の最も強力な機能の 1 つは、高度な検索です。 高度な狩猟に慣れていない場合は、高度な狩猟で脅威を積極的 [に探す方法を参照してください](advanced-hunting-overview.md)。

高度な検索はクエリ ベース (Kusto Query Language) の脅威検索ツールで、デバイスから Defender for Endpoint が収集するキャプチャされた (生の) データの最大 30 日間を探索できます。 高度な検索を通じて、イベントを積極的に検査して、興味深いインジケーターとエンティティを見つけ出します。 データへの柔軟なアクセスは、既知の脅威と潜在的な脅威の両方に対する抑制されていない検出に役立ちます。

高度な検索を通じて、ASR ルール情報を抽出し、レポートを作成し、特定の ASR ルール監査またはブロック イベントのコンテキストに関する詳細な情報を取得できます。

ASR ルール イベントは、デバイス の詳細な検索セクションの DeviceEvents テーブルからクエリを実行Microsoft 365 Defender。 たとえば、次のような単純なクエリは、過去 30 日間、ASR ルールをデータ ソースとして持つすべてのイベントをレポートし、アクションタイプカウントで集計します。この場合は ASR ルールの実際のコード名になります。

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高度な検索クエリ。":::

:::image type="content" source="images/adv-hunt-sc-2new.png" lightbox="images/adv-hunt-sc-2new.png" alt-text="高度なハンティング画面。":::

高度な検索を使用すると、個別のコンピューターで何かを特定するか、環境全体から分析情報を抽出するかに関係なく、何が起こっているかを確認するために、好みでクエリを形成できます。

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Microsoft Defender for Endpoint machine Timeline

高度な検索に代わる方法ですが、スコープが狭い場合は、Microsoft Defender for Endpoint マシンのタイムラインを使用します。 Microsoft 365 Defender で過去 6 か月間、デバイスのすべての収集イベントを表示するには、[コンピューター] リストに移動し、特定のコンピューターを選択し、[タイムライン] タブをクリックします。

次の図は、特定のエンドポイントでこれらのイベントのタイムライン ビューのスクリーンショットです。 このビューから、右側のウィンドウに沿ったイベント グループに基づいてイベント リストをフィルター処理できます。 アラートを表示したり、履歴タイムラインをスクロールしたりしながら、フラグ付きイベントと詳細イベントを有効または無効にすることもできます。

:::image type="content" source="images/mic-sec-def-timelinenew.png" lightbox="images/mic-sec-def-timelinenew.png" alt-text="Microsoft 365 Defenderタイムライン。":::

## <a name="how-to-troubleshoot-asr-rules"></a>ASR ルールのトラブルシューティング方法

最初の方法と最も直接的な方法は、powerShell コマンドレットを使用して、ASR ルールが有効になっている (およびそれらの構成) Windows デバイスでローカルで確認する方法です。

ASR ルールの影響と運用をトラブルシューティングするために、Windows提供するその他の情報源を次に示します。

### <a name="querying-which-rules-are-active"></a>アクティブなルールのクエリ

ASR ルールが既に有効になっているかどうかを判断する最も簡単な方法の 1 つは、PowerShell コマンドレット Get-MpPreference です。

次に例を示します。

:::image type="content" source="images/getmpreferencescriptnew.png" lightbox="images/getmpreferencescriptnew.png" alt-text="mppreference スクリプトを取得します。":::

複数の ASR ルールがアクティブで、構成されたアクションが異なります。

ASR ルールに関する上記の情報を展開するには、ASR ルールのプロパティAttackSurfaceReductionRules_Idsおよび/**または****AttackSurfaceReductionRules_Actions。**

例:

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference の例を取得します。":::

上記は、0 (Not Configured) とは異なる設定を持つ ASR ルールのすべての ID を示しています。

次に、各ルールが構成されている実際のアクション (ブロックまたは監査) を一覧表示します。

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="mppreference の例 2 を取得します。":::

### <a name="querying-blocking-and-auditing-events"></a>ブロックイベントと監査イベントのクエリ

ASR ルール イベントは、ログ内でWindows Defenderできます。

アクセスするには、イベント ビューアー Windows開き、[アプリケーションとサービスログ] Microsoft Windows Windows Defender \>  \>  \>  \> **を参照します**。

:::image type="content" source="images/eventviewerscrnew.png" lightbox="images/eventviewerscrnew.png" alt-text="イベント ビューアー scr。":::

## <a name="microsoft-defender-antimalware-protection-logs"></a>Microsoft Defender マルウェア対策保護ログ

また、必要に応じてタスクを管理および構成および自動化するために使用できる、Microsoft Defender ウイルス対策 専用のコマンド ライン ツールを使用してルール イベント `*mpcmdrun.exe*` を表示することもできます。

このユーティリティは *、%ProgramFiles%\Windows Defender\MpCmdRun.exeにあります*。 管理者特権のコマンド プロンプト (管理者として実行) から実行する必要があります。

サポート情報を生成するには *、-getfilesMpCmdRun.exeを入力します*。 しばらくすると、いくつかのログがアーカイブ (MpSupportFiles.cab) にパッケージ化され *、C:\ProgramData\Microsoft\Windows Defender\Support で使用できます*。

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="マルウェア保護ログ。":::

そのアーカイブを抽出すると、トラブルシューティングの目的で多くのファイルを利用できます。

最も関連性の高いファイルは次のとおりです。

- **MPOperationalEvents.txt**: このファイルには、イベント ビューアーで見つかった同じレベルの情報が、Windows Defenderの操作ログに含まれます。
- **MPRegistry.txt**: このファイルでは、サポート ログがキャプチャされた時点から、現在Windows Defender構成を分析できます。
- **MPLog.txt**: このログには、すべてのアクション/操作に関する詳細な情報がWindows Defender。

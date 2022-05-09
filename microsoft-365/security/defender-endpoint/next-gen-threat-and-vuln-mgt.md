---
title: 脅威と脆弱性の管理
description: この新機能では、エンドポイントの脆弱性と構成ミスの検出、優先順位付け、修復に対して、ゲームを変えるリスクベースのアプローチを使用します。
keywords: 脅威& 脆弱性の管理、脅威と脆弱性の管理、Microsoft Defender for Endpoint TVM、Microsoft Defender for Endpoint-TVM、脆弱性の管理、脆弱性評価、脅威と脆弱性のスキャン、セキュリティで保護された構成の評価、Microsoft Defender for Endpoint、エンドポイントの脆弱性、次世代
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 1e37c20bf6bd9b31bd255d2ec47ea87cb219f66a
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167060"
---
# <a name="threat-and-vulnerability-management"></a>脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

エンドポイントの弱点を効果的に特定、評価、修復することは、健全なセキュリティ プログラムを実行し、組織のリスクを軽減する上で極めて重要です。 脅威と脆弱性の管理は、組織の暴露を削減し、エンドポイントの役割を強化し、組織の回復性を向上させるためのインフラストラクチャとして機能します。

エージェントや定期的なスキャンを必要とせずに、センサーを使用してリアルタイムで脆弱性と構成ミスを検出します。 脅威の状況、組織内の検出、脆弱なデバイスに関する機密情報、ビジネス コンテキストに基づいて、脆弱性の優先順位を付けます。

脅威と脆弱性の管理の概要については、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>ワークフローのギャップを埋める

脅威と脆弱性の管理は、組み込み、リアルタイム、クラウドを使用して構築されます。 Microsoft エンドポイント セキュリティ スタック、Microsoft Intelligent Security Graph、およびアプリケーション分析サポート情報と完全に統合されています。

脆弱性管理は、修復プロセス中にセキュリティ管理と IT 管理の間のギャップを埋める業界初のソリューションです。 Microsoft IntuneとMicrosoft Endpoint Configuration Managerと統合して、セキュリティ タスクまたはチケットを作成します。

### <a name="real-time-discovery"></a>リアルタイム検出

エンドポイントの脆弱性と構成ミスを検出するために、脅威と脆弱性の管理は同じエージェントレス組み込みの Defender for Endpoint センサーを使用して、煩雑なネットワーク スキャンと IT オーバーヘッドを減らします。

また、次の機能も提供します。

- **リアルタイム デバイスのインベントリ** - Defender for Endpoint にオンボードされたデバイスは、脆弱性やセキュリティ構成のデータを自動的にレポートし、ダッシュボードにプッシュ転送します。
- **ソフトウェアと脆弱性の可視化** - 組織のソフトウェア インベントリや、インストール、アンインストール、パッチなどのソフトウェアの変更を光学的に確認します。 新たに発見された脆弱性は、1 次および 3 次アプリケーションに対する軽減策の推奨事項とともに報告されます。
- **アプリケーションのランタイム コンテキスト** - アプリケーションの使用状況パターンを可視化し、優先順位付けと意思決定を改善します。
- **構成の状態** - 組織のセキュリティ構成や設定の誤りを可視化します。 問題点は、実行可能なセキュリティに関する推奨事項とともにダッシュボードに報告されます。

### <a name="intelligence-driven-prioritization"></a>インテリジェンス主導の優先順位付け

脅威と脆弱性の管理は、組織にとって最も緊急でリスクの高い弱点に優先順位を付け、焦点を当てるのに役立ちます。 セキュリティに関する推奨事項と、動的な脅威とビジネス コンテキストが融合されています。

- **新たな攻撃を大規模に公開** する - セキュリティに関する推奨事項の優先順位を動的に調整します。 脅威と脆弱性の管理は、現在、最もリスクの高い脅威が発生している、最新の脅威で現在悪用されている脆弱性に焦点を当てています。
- **アクティブな違反を特定する** - 脅威と脆弱性の管理とEDRの分析情報を関連付けて、組織内のアクティブな違反で悪用される脆弱性の優先順位を付けます。
- **価値の高い資産を保護する** - ビジネスクリティカルなアプリケーション、機密データ、または価値の高いユーザーで公開されているデバイスを識別します。

### <a name="seamless-remediation"></a>シームレスな修復

脅威と脆弱性の管理により、セキュリティ管理者と IT 管理者はシームレスに共同作業して問題を修復できます。

- **IT に送信された修復要求** - 特定のセキュリティ推奨事項からMicrosoft Intuneで修復タスクを作成します。 この機能を他の IT セキュリティ管理プラットフォームに拡張する予定です。
- **代替の軽減策** - ソフトウェアの脆弱性に関連するリスクを軽減できる構成変更など、追加の軽減策に関する分析情報を得る。
- **リアルタイム修復状態** - 組織全体の修復アクティビティの状態と進行状況をリアルタイムで監視します。

## <a name="threat-and-vulnerability-management-walk-through"></a>脅威と脆弱性の管理のウォークスルー

脅威と脆弱性の管理の包括的なチュートリアルについては、このビデオをご覧ください。

> [!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>ナビゲーション ウィンドウ 

<br>

****

|分野|説明|
|---|---|
|**ダッシュボード**|組織の公開スコア、Microsoft Secure Score for Devices、デバイス公開の分布、セキュリティに関する推奨事項、脆弱なソフトウェアの上位、修復アクティビティの上位、および公開された上位のデバイス データの概要を確認します。|
|[**セキュリティに関する推奨事項**](tvm-security-recommendation.md)|セキュリティに関する推奨事項と関連する脅威情報の一覧を参照してください。 一覧から項目を選択すると、ポップアップ パネルが開き、脆弱性の詳細、ソフトウェア ページを開くリンク、修復オプションと例外オプションが表示されます。 デバイスがAzure Active Directory経由で参加していて、Defender for Endpoint でIntune接続を有効にしている場合は、Intuneでチケットを開くこともできます。|
|[**修復**](tvm-remediation.md)|作成した修復アクティビティと推奨事項の例外を確認します。|
|[**ソフトウェア インベントリ**](tvm-software-inventory.md)|組織内の脆弱なソフトウェアの一覧と、弱点と脅威の情報を参照してください。|
|[**弱点**](tvm-weaknesses.md)|組織内の一般的な脆弱性と露出 (CVE) の一覧を参照してください。|
|[**イベントのタイムライン**](threat-and-vuln-mgt-event-timeline.md)|組織のリスクに影響を与える可能性のあるイベントを表示します。|
|||

## <a name="apis"></a>API

脅威と脆弱性の管理関連の API 呼び出しを実行して、脆弱性の管理ワークフローを自動化します。 この [Microsoft Tech Communityブログ投稿](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)から詳細を確認してください。

関連する API については、次の記事を参照してください。

- [サポート対象 Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [コンピューター API](machine.md)
- [推奨事項 API](vulnerability.md)
- [API のスコア付け](score.md)
- [ソフトウェア API](software.md)
- [脆弱性 API](vulnerability.md)
- [マシンとソフトウェアによる脆弱性の一覧表示](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a>関連項目

- [サポート対象オペレーティング システムとプラットフォーム](tvm-supported-os.md)
- [脅威と脆弱性の管理ダッシュボード](tvm-dashboard-insights.md)
- [ブログ: Microsoft の脅威&脆弱性管理により、数千人の顧客が脆弱性をリアルタイムで検出、優先順位付け、修復できるようになりました](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)

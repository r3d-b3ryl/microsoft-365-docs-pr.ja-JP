---
title: 脅威と脆弱性の管理
description: この新しい機能では、エンドポイントの脆弱性と誤った構成の検出、事前設定、修復に対して、ゲームを変えるリスクベースのアプローチを使用します。
keywords: threat & 脆弱性の管理, 脅威と脆弱性の管理, Microsoft Defender for Endpoint TVM, Microsoft Defender for Endpoint-TVM, 脆弱性の管理, 脆弱性評価, 脅威と脆弱性スキャン, セキュリティで保護された構成評価, Microsoft Defender for Endpoint, endpoint の脆弱性, 次世代
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
ms.openlocfilehash: 54c198470d7fd3ee0a05ff40c7597018735b4e3b
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881695"
---
# <a name="threat-and-vulnerability-management"></a>脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

エンドポイントの弱点を効果的に特定、評価、修復するには、健全なセキュリティ プログラムを実行し、組織のリスクを軽減する上で極めて重要です。 脅威と脆弱性の管理は、組織の暴露を削減し、エンドポイントの役割を強化し、組織の回復性を向上させるためのインフラストラクチャとして機能します。

センサーを使用して、エージェントや定期的なスキャンを必要とせずに、脆弱性と誤った構成をリアルタイムで検出します。 脅威の状況、組織内の検出、脆弱なデバイスに関する機密情報、およびビジネス コンテキストに基づいて脆弱性の優先順位を設定します。

詳細については、このビデオをご覧脅威と脆弱性の管理。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>ワークフローのギャップを埋める

脅威と脆弱性の管理は、リアルタイムで構築され、クラウドに対応しています。 Microsoft エンドポイント セキュリティ スタック、Microsoft Intelligent Security Graph、およびアプリケーション分析のナレッジ ベースと完全に統合されています。

脆弱性管理は、修復プロセス中にセキュリティ管理と IT 管理の間のギャップを埋める業界初のソリューションです。 セキュリティ タスクまたはチケットを作成するには、セキュリティ タスクとMicrosoft IntuneとMicrosoft Endpoint Configuration Manager。

### <a name="real-time-discovery"></a>リアルタイム検出

エンドポイントの脆弱性と構成の誤りを検出するために、脅威と脆弱性の管理 は同じエージェントレス組み込みの Defender for Endpoint センサーを使用して、面倒なネットワーク スキャンと IT オーバーヘッドを削減します。

また、次の機能も提供します。

- **リアルタイム デバイスのインベントリ** - Defender for Endpoint にオンボードされたデバイスは、脆弱性やセキュリティ構成のデータを自動的にレポートし、ダッシュボードにプッシュ転送します。
- **ソフトウェアと脆弱性の可視化** - 組織のソフトウェア インベントリや、インストール、アンインストール、パッチなどのソフトウェアの変更を光学的に確認します。 新たに発見された脆弱性は、1 次および 3 次アプリケーションに対する軽減策の推奨事項とともに報告されます。
- **アプリケーションのランタイム コンテキスト** - アプリケーションの使用状況パターンを可視化し、優先順位付けと意思決定を改善します。
- **構成の状態** - 組織のセキュリティ構成や設定の誤りを可視化します。 問題点は、実行可能なセキュリティに関する推奨事項とともにダッシュボードに報告されます。

### <a name="intelligence-driven-prioritization"></a>インテリジェンスによる事前設定

脅威と脆弱性の管理は、お客様が組織に最も緊急かつ最も高いリスクを与える弱点に優先順位を付け、集中するのに役立ちます。 セキュリティに関する推奨事項と動的な脅威とビジネス コンテキストを融合します。

- **新しい攻撃を野生で** 公開する - セキュリティ推奨事項の事前設定を動的に調整します。 脅威と脆弱性の管理は、最もリスクの高い、新しい脅威で現在悪用されている脆弱性に焦点を当て、
- **アクティブな侵害を特定** する - 脅威と脆弱性の管理とEDRを関連付け、組織内のアクティブな侵害で悪用される脆弱性を優先順位付けします。
- **価値の高い資産の** 保護 - ビジネスクリティカルなアプリケーション、機密データ、または価値の高いユーザーを使用して、公開されているデバイスを特定します。

### <a name="seamless-remediation"></a>シームレスな修復

脅威と脆弱性の管理により、セキュリティ管理者と IT 管理者はシームレスに共同作業して問題を修復できます。

- **IT に送信される修復要求**- 特定のセキュリティ推奨事項からMicrosoft Intune修復タスクを作成します。 この機能を他の IT セキュリティ管理プラットフォームに拡張する予定です。
- **代替の軽減** 策 - ソフトウェアの脆弱性に関連するリスクを軽減できる構成の変更など、追加の軽減策に関する洞察を得る。
- **リアルタイムの修復状態** - 組織全体の修復アクティビティの状態と進捗状況をリアルタイムで監視します。

## <a name="threat-and-vulnerability-management-walk-through"></a>脅威と脆弱性の管理のウォークスルー

このビデオでは、このビデオを参照して、詳細な脅威と脆弱性の管理。

> [!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>ナビゲーション ウィンドウ 

<br>

****

|分野|説明|
|---|---|
|**ダッシュボード**|組織の露出スコア、Microsoft Secure Score for Devices、デバイスの露出分布、トップ セキュリティ推奨事項、脆弱なソフトウェアの上位、トップ修復アクティビティ、および公開されているデバイス データの上位レベルのビューを取得します。|
|[**セキュリティに関する推奨事項**](tvm-security-recommendation.md)|セキュリティに関する推奨事項と関連する脅威情報の一覧を参照してください。 リストからアイテムを選択すると、フライアウト パネルが開き、脆弱性の詳細、ソフトウェア ページを開くリンク、修復と例外のオプションが表示されます。 デバイスがエンドポイント経由で参加し、Defender for Endpoint で Intune 接続を有効にしている場合Azure Active Directory Intune でチケットを開く方法もできます。|
|[**修復**](tvm-remediation.md)|作成した修復アクティビティと推奨事項の例外を参照してください。|
|[**ソフトウェア インベントリ**](tvm-software-inventory.md)|組織内の脆弱なソフトウェアの一覧と、弱点と脅威に関する情報を参照してください。|
|[**弱点**](tvm-weaknesses.md)|組織の一般的な脆弱性と露出 (CVEs) の一覧を参照してください。|
|[**イベントのタイムライン**](threat-and-vuln-mgt-event-timeline.md)|組織のリスクに影響を与える可能性があるイベントを表示します。|
|||

## <a name="apis"></a>API

関連脅威と脆弱性の管理 API 呼び出しを実行して、ワークフロー脆弱性の管理自動化します。 詳細については、[この Microsoft Tech のブログCommunityを参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。

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
- [ブログ: Microsoft の脅威&脆弱性管理は、何千人もの顧客が脆弱性をリアルタイムで検出、優先順位付け、修復するのに役立ちます](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)

---
title: 脅威と脆弱性の管理
description: この新しい機能では、エンドポイントの脆弱性と誤った構成の検出、事前設定、修復に対して、ゲームを変えるリスクベースのアプローチを使用します。
keywords: Threat & の脆弱性管理、脅威と脆弱性の管理、Microsoft Defender for Endpoint TVM、Microsoft Defender for Endpoint-TVM、脆弱性管理、脆弱性評価、脅威と脆弱性のスキャン、セキュリティで保護された構成評価、Microsoft Defender for Endpoint、エンドポイントの脆弱性、次世代
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934167"
---
# <a name="threat-and-vulnerability-management"></a>脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

エンドポイントの弱点を効果的に特定、評価、修復するには、健全なセキュリティ プログラムを実行し、組織のリスクを軽減する上で極めて重要です。 脅威と脆弱性の管理は、組織の暴露を削減し、エンドポイントの役割を強化し、組織の回復性を向上させるためのインフラストラクチャとして機能します。

センサーを使用して、エージェントや定期的なスキャンを必要とせずに、脆弱性と誤った構成をリアルタイムで検出します。 脅威の状況、組織内の検出、脆弱なデバイスに関する機密情報、およびビジネス コンテキストに基づいて脆弱性の優先順位を設定します。

脅威と脆弱性の管理の概要については、このビデオをご覧ください。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>ワークフローのギャップを埋める

脅威と脆弱性の管理は、リアルタイムで構築され、クラウドに対応しています。 Microsoft エンドポイント セキュリティ スタック、Microsoft インテリジェント セキュリティ グラフ、およびアプリケーション分析のナレッジ ベースと完全に統合されています。  

脆弱性管理は、修復プロセス中にセキュリティ管理と IT 管理の間のギャップを埋める業界初のソリューションです。 Microsoft Intune および Microsoft Endpoint Configuration Manager と統合して、セキュリティ タスクまたはチケットを作成します。

### <a name="real-time-discovery"></a>リアルタイム検出

エンドポイントの脆弱性と誤った構成を検出するために、脅威と脆弱性の管理では、同じエージェントレス組み込みの Defender for Endpoint センサーを使用して、面倒なネットワーク スキャンと IT オーバーヘッドを削減します。

また、次の機能も提供します。

- **リアルタイム デバイス インベントリ** - Defender for Endpoint にオンボードされたデバイスは、脆弱性とセキュリティ構成データをダッシュボードに自動的に報告してプッシュします。
- **ソフトウェアと脆弱性の** 可視化 - 組織のソフトウェア インベントリへのオプティクス、インストール、アンインストール、パッチなど、ソフトウェアの変更。 新たに発見された脆弱性は、第 1 および第 3 者のアプリケーションに対する対処可能な軽減策の推奨事項で報告されます。
- **アプリケーション ランタイム コンテキスト** - アプリケーションの使用状況パターンを表示して、より良い事前設定と意思決定を行います。
- **構成の体制** - 組織のセキュリティ構成または構成の誤りを表示します。 問題はダッシュボードで報告されます。セキュリティに関する推奨事項を実行できます。

### <a name="intelligence-driven-prioritization"></a>インテリジェンスによる事前設定

脅威と脆弱性の管理は、お客様が組織にとって最も緊急かつ最もリスクの高い弱点に優先順位を付け、集中するのに役立ちます。 セキュリティに関する推奨事項と動的な脅威とビジネス コンテキストを融合します。

- **新しい攻撃を野生で** 公開する - セキュリティ推奨事項の事前設定を動的に調整します。 脅威と脆弱性の管理では、現在、最もリスクの高い、新しい脅威で悪用されている脆弱性に焦点を当てて、リスクが最も高い。
- **アクティブな侵害を特定** する - 脅威と脆弱性の管理と EDR の分析情報を関連付け、組織内のアクティブな侵害で悪用される脆弱性の優先順位を設定します。
- **価値の高い資産の** 保護 - ビジネスクリティカルなアプリケーション、機密データ、または価値の高いユーザーを使用して、公開されているデバイスを特定します。

### <a name="seamless-remediation"></a>シームレスな修復

脅威と脆弱性の管理により、セキュリティ管理者と IT 管理者はシームレスに共同作業して問題を修復できます。

- **IT に送信される修復要求** - 特定のセキュリティ推奨事項から Microsoft Intune で修復タスクを作成します。 この機能を他の IT セキュリティ管理プラットフォームに拡張する予定です。
- **代替の軽減** 策 - ソフトウェアの脆弱性に関連するリスクを軽減できる構成の変更など、追加の軽減策に関する洞察を得る。
- **リアルタイムの修復状態** - 組織全体の修復アクティビティの状態と進捗状況をリアルタイムで監視します。

## <a name="threat-and-vulnerability-management-walk-through"></a>脅威と脆弱性管理のウォークスルー

脅威と脆弱性の管理に関する包括的なウォークスルーについては、このビデオをご覧ください。

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>ナビゲーション ウィンドウ 

分野 | 説明
:---|:---
**ダッシュボード**   | 組織の露出スコア、Microsoft Secure Score for Devices、デバイスの露出分布、トップ セキュリティ推奨事項、脆弱なソフトウェアの上位、トップ修復アクティビティ、および公開されているデバイス データの上位レベルのビューを取得します。
[**セキュリティ上の推奨事項**](tvm-security-recommendation.md) | セキュリティに関する推奨事項と関連する脅威情報の一覧を参照してください。 リストからアイテムを選択すると、フライアウト パネルが開き、脆弱性の詳細、ソフトウェア ページを開くリンク、修復と例外のオプションが表示されます。 デバイスが Azure Active Directory を介して参加し、Defender for Endpoint で Intune 接続を有効にしている場合は、Intune でチケットを開く方法もできます。
[**修復**](tvm-remediation.md) | 作成した修復アクティビティと推奨事項の例外を参照してください。
[**ソフトウェア インベントリ**](tvm-software-inventory.md) | 組織内の脆弱なソフトウェアの一覧と、弱点と脅威に関する情報を参照してください。
[**弱点**](tvm-weaknesses.md) | 組織の一般的な脆弱性と露出 (CVEs) の一覧を参照してください。
[**イベントのタイムライン**](threat-and-vuln-mgt-event-timeline.md) | 組織のリスクに影響を与える可能性があるイベントを表示します。

## <a name="apis"></a>API

脅威と脆弱性管理に関連する API 呼び出しを実行して、脆弱性管理ワークフローを自動化します。 詳細については [、Microsoft Tech Community のブログ投稿をご覧ください](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。

関連する API については、次の記事を参照してください。

- [サポート対象 Microsoft Defender for Endpoint API](exposed-apis-list.md)
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

---
title: Microsoft Defender for Endpoint 展開の準備
description: Microsoft Defender for Endpoint を展開するために、関係者の承認、タイムライン、環境に関する考慮事項、導入順序を準備する
keywords: 展開、準備、関係者、タイムライン、環境、エンドポイント、サーバー、管理、導入
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 49e4fa7d283219c3eaf981184f1239cf80534e38
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166088"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Microsoft Defender for Endpoint 展開の準備

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint の展開は、次の 3 フェーズプロセスです。

|![展開フェーズ - 準備します。](images/phase-diagrams/prepare.png)<br>フェーズ 1: 準備|[![展開フェーズ - セットアップ](images/phase-diagrams/setup.png)](production-deployment.md)<br>[フェーズ 2: セットアップ](production-deployment.md)|[![展開フェーズ - オンボード](images/phase-diagrams/onboard.png)](onboarding.md)<br>[フェーズ 3: オンボード](onboarding.md)|
|---|---|---|
|*お前はここにいる!*|||

現在、準備段階です。

正常に展開するには、準備が重要です。 この記事では、Defender for Endpoint の展開を準備する際に考慮する必要があるポイントについて説明します。

## <a name="stakeholders-and-approval"></a>利害関係者と承認

次のセクションでは、プロジェクトに関与し、承認、レビュー、または情報を得る必要があるすべての関係者を特定します。

組織に応じて、以下の表に関係者を追加します。

- SO = プロジェクトの承認
- R = このプロジェクトを確認し、入力を提供する
- I = このプロジェクトの通知

<br>

****

|名前|役割|アクション|
|---|---|---|
|名前とメールを入力する|**最高情報セキュリティ責任者 (CISO)** 新しいテクノロジ展開の組織の内部でスポンサーを務め、役員 *の代表者。*|だから|
|名前とメールを入力する|**サイバー防御運用センター (CDOC)** の代表は *、CDOC* チームの担当者で、この変更が顧客のセキュリティ運用チームのプロセスとどのように一致するのか定義します。|だから|
|名前とメールを入力する|**セキュリティ アーキ***テクト* この変更が組織内の主要なセキュリティ アーキテクチャとどのように一致するのか定義するセキュリティ チームの担当者。|R|
|名前とメールを入力する|**Workplace Architect** *この変更が* 組織内のコアワークプレース アーキテクチャとどのように対応されるかを定義する IT チームの担当者。|R|
|名前とメールを入力する|**セキュリティ アナリスト***セキュリティ運用の* 観点から、この変更の検出機能、ユーザー エクスペリエンス、および全体的な役に立つ情報を提供できる CDOC チームの担当者。|I|
||||

## <a name="environment"></a>環境

このセクションは、環境が関係者によって深く理解され、テクノロジやプロセスに必要な潜在的な依存関係や変更を特定するのに役立ちます。

<br>

****

|内容|説明|
|---|---|
|エンドポイント数|オペレーティング システム別のエンドポイントの総数。|
|サーバー数|オペレーティング システムのバージョン別のサーバーの総数。|
|管理エンジン|管理エンジンの名前とバージョン (たとえば、現在System Center Configuration Manager 1803)。|
|CDOC 配布|高レベルの CDOC 構造 (たとえば、Contoso にアウトソーシングされた Tier 1、ヨーロッパとアジアに分散した Tier 2、Tier 3 のインハウス)。|
|セキュリティ情報とイベント (SIEM)|SIEM テクノロジが使用されています。|
|||

## <a name="role-based-access-control"></a>役割ベースのアクセス制御

最小特権の概念の使用をお勧めします。 Defender for Endpoint は、アプリケーション内の組み込みの役割Azure Active Directory。 Microsoft では [、利用可能なさまざまな役割を確認](/azure/active-directory/roles/permissions-reference) し、このアプリケーションの各ペルサのニーズを解決するために適切な役割を選択してください。 一部の役割は、展開が完了した後に一時的に適用して削除する必要がある場合があります。

<br>

****

|Personas|役割|Azure ADロール (必要に応じて)|に割り当てる|
|---|---|---|---|
|セキュリティ管理者||||
|セキュリティ アナリスト||||
|エンドポイント管理者||||
|インフラストラクチャ管理者||||
|ビジネス所有者/利害関係者||||
|

Microsoft では[、Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)を使用して、ディレクトリアクセス許可を持つユーザーに対して追加の監査、制御、およびアクセスレビューを提供するために、ロールを管理します。

Defender for Endpoint では、アクセス許可を管理する 2 つの方法がサポートされています。

- **基本的なアクセス許可の管理**: アクセス許可をフル アクセスまたは読み取り専用に設定します。 Azure Active Directory の Globa Administrator または Security Administrator ロールを持つ基本的なアクセス許可管理ユーザーの場合、セキュリティ リーダーの役割には読み取り専用アクセス権があります。

- **役割ベースのアクセス制御 (RBAC)**: 役割を定義し、Azure AD ユーザー グループを役割に割り当て、ユーザー グループにデバイス グループへのアクセス権を付与することで、詳細なアクセス許可を設定します。 詳細については、次の情報を参照してください。 「役割 [ベースのアクセス制御を使用したポータル アクセスの管理」を参照してください](rbac.md)。

ビジネス上の正当性を持つユーザーだけが Defender for Endpoint にアクセスできるよう RBAC を活用する方法をお勧めします。

アクセス許可のガイドラインの詳細については、「役割を作成し、役割をグループに割り当てる」[をAzure Active Directoryできます](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)。

次の表の例では、環境に必要な RBAC 構造を特定するのに役立つ、環境内のサイバー防御操作センター構造を識別します。

<br>

****

|階層|説明|アクセス許可が必要|
|---|---|---|
|階層 1|**ローカル セキュリティ運用チーム / IT チーム** <p> このチームは通常、地理的位置内に含まれるアラートをトリアージして調査し、アクティブな修復が必要な場合は階層 2 にエスカレートします。||
|階層 2|**地域のセキュリティ運用チーム** <p> このチームは、地域のすべてのデバイスを表示し、修復アクションを実行できます。|データを表示|
|階層 3|**グローバル セキュリティ運用チーム** <p> このチームはセキュリティ専門家で構成され、ポータルからすべてのアクションを表示して実行する権限があります。|データを表示 <p> アラートの調査 アクティブな修復アクション <p> アラートの調査 アクティブな修復アクション <p> ポータル システム設定の管理 <p> セキュリティ設定の管理|
||||

## <a name="adoption-order"></a>導入順序

多くの場合、組織には既存のエンドポイント セキュリティ製品が配置されます。 すべての組織がウイルス対策ソリューションである必要があります。 ただし、組織が既にソリューションを埋め込EDR場合があります。

以前は、アプリケーション層とインフラストラクチャの依存関係が厳しいので、時間がかかり、達成が困難であったセキュリティ ソリューションを置き換えるのは困難でした。 ただし、Defender for Endpoint はオペレーティング システムに組み込むため、サード パーティ製ソリューションの置き換えは簡単に実現できます。

使用する Defender for Endpoint のコンポーネントを選択し、適用されないコンポーネントを削除します。 次の表は、エンドポイント セキュリティ スイートを有効にする方法について Microsoft が推奨する順序を示しています。

<br>

****

|コンポーネント|説明|導入順序ランク|
|---|---|---|
|エンドポイント検出&応答 (EDR)|Defender for Endpoint endpoint detection and response capabilitis provide advanced attack detections are near real-time and actionable. セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。 <p> [詳細情報](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)|1|
|脅威&脆弱性管理 (TVM)|脅威&脆弱性管理は、Microsoft Defender for Endpoint のコンポーネントであり、セキュリティ管理者とセキュリティ運用チームの両方に、次の固有の値を提供します。 <ul><li>エンドポイントの脆弱性に関連したリアルタイムのエンドポイント検出と応答（EDR）の分析</li><li>インシデント調査中の貴重なデバイスの脆弱性コンテキスト</li><li>組み込みの修復プロセスは、Microsoft Intuneおよび Microsoft System Center Configuration Manager</li></ul> <p> [詳細情報](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845) を参照してください。|2|
|次世代保護 (NGP)|Microsoft Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、およびサーバーに次世代の保護を提供する組み込みのマルウェア対策ソリューションです。 Microsoft Defender ウイルス対策には、次のものが含まれます。 <ul><li>新たに出現する脅威をほぼ瞬時に検出し、ブロックするためのクラウドによる保護。 機械学習やインテリジェント セキュリティ グラフに加えて、クラウドによる保護は Microsoft Defender ウイルス対策を強化する次世代テクノロジの一部です。</li><li>高度なファイルとプロセスの動作の監視、その他のヒューリスティック ("リアルタイム保護" とも呼ばれる) を使用した常時スキャン。</li><li>機械学習、手動および自動のビッグデータ分析、徹底した脅威耐性調査に基づいた専用の保護の更新。</li></ul> <p> [詳細情報](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) を参照してください。|3|
|攻撃表面の縮小 (ASR)|Microsoft Defender for Endpoint の攻撃表面の縮小機能は、新しい脅威や新たな脅威から組織内のデバイスとアプリケーションを保護するのに役立ちます。 <br> [詳細情報](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)|4|
|自動調査&修復 (AIR)|Microsoft Defender for Endpoint では、自動調査を使用して、個別に調査する必要があるアラートの量を大幅に削減します。 自動調査機能は、さまざまな検査アルゴリズムと、アナリストが使用するプロセス (プレイブックなど) を活用してアラートを調べ、違反を解決するために直ちに修復アクションを実行します。 これにより、アラート量が大幅に削減され、セキュリティ運用の専門家は、より高度な脅威やその他の価値の高い業務に集中できるようになります。 <p> [詳細情報](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)|×|
|Microsoft 脅威エキスパート (MTE)|Microsoft 脅威エキスパートは、セキュリティ オペレーション センター (SOC) にエキスパート レベルの監視と分析を提供するマネージ ハンティング サービスで、固有の環境における重大な脅威を見逃すのを防いでお手伝いします。 <p> [詳細情報](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)|×|

## <a name="next-step"></a>次の手順

![フェーズ 2: セットアップ。](images/setup.png) <br> [フェーズ 2: セットアップ](production-deployment.md)

Microsoft Defender for Endpoint の展開をセットアップします。

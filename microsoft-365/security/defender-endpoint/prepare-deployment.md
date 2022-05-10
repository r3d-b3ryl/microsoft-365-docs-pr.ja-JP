---
title: Microsoft Defender for Endpoint 展開の準備
description: Microsoft Defender for Endpointを展開するための利害関係者の承認、タイムライン、環境に関する考慮事項、導入順序を準備する
keywords: デプロイ、準備、関係者、タイムライン、環境、エンドポイント、サーバー、管理、導入
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
ms.openlocfilehash: 29f9aabf2c0345e46123ba76869718c15d8d1885
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806218"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Microsoft Defender for Endpoint 展開の準備

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint のデプロイは、次の 3 フェーズのプロセスです。

|![デプロイ フェーズ - 準備します。](images/phase-diagrams/prepare.png)<br>フェーズ 1: 準備|[![デプロイ フェーズ - セットアップ](images/phase-diagrams/setup.png)](production-deployment.md)<br>[フェーズ 2: セットアップ](production-deployment.md)|[![デプロイ フェーズ - オンボード](images/phase-diagrams/onboard.png)](onboarding.md)<br>[フェーズ 3: オンボード](onboarding.md)|
|---|---|---|
|*お客様はここにいます。*|||

現在準備段階です。

正常に展開するには、準備が重要です。 この記事では、Defender for Endpoint をデプロイする準備をするときに考慮する必要があるポイントについて説明します。

## <a name="stakeholders-and-approval"></a>利害関係者と承認

次のセクションは、プロジェクトに関与し、承認、レビュー、または情報を得る必要があるすべての利害関係者を特定する役割を果たします。

組織に合わせて、次の表に関係者を追加します。

- SO = プロジェクトの承認
- R = このプロジェクトを確認し、入力を指定する
- I = このプロジェクトの通知

<br>

****

|名前|役割|Action|
|---|---|---|
|名前とメールを入力する|**最高情報セキュリティ責任者 (CISO)** *新しいテクノロジの展開のために組織内でスポンサーを務めるエグゼクティブ担当者。*|だから|
|名前とメールを入力する|**Cyber Defense Operations Center (CDOC) の責任者 CDOC** *チームの担当者は、この変更を顧客のセキュリティ運用チームのプロセスとどのように連携させるかを定義する責任者です。*|だから|
|名前とメールを入力する|**Security Architect** *この変更を組織内のコア セキュリティ アーキテクチャとどのように連携させるかを定義する担当のセキュリティ チームの担当者。*|R|
|名前とメールを入力する|**Workplace Architect** *この変更を組織内のコア ワークプレース アーキテクチャとどのように連携させるかを定義する IT チームの担当者。*|R|
|名前とメールを入力する|**セキュリティ アナリスト** この *変更の検出機能、ユーザー エクスペリエンス、および全体的な有用性に関する情報をセキュリティ操作の観点から提供できる CDOC チームの担当者。*|I|
||||

## <a name="environment"></a>環境

このセクションは、テクノロジやプロセスに必要な潜在的な依存関係や変更を特定するのに役立つ、利害関係者が環境を深く理解するために使用されます。

<br>

****

|内容|説明|
|---|---|
|エンドポイント数|オペレーティング システムごとのエンドポイントの合計数。|
|サーバー数|オペレーティング システムのバージョン別のサーバーの合計数。|
|管理エンジン|管理エンジンの名前とバージョン (現在のブランチ 1803 System Center Configuration Managerなど)。|
|CDOC 分布|高レベルの CDOC 構造 (たとえば、Contoso にアウトソーシングされた階層 1、層 2、階層 3 は、ヨーロッパとアジアに分散しています)。|
|セキュリティ情報とイベント (SIEM)|使用中の SIEM テクノロジ。|
|||

## <a name="role-based-access-control"></a>役割ベースのアクセス制御

Microsoft では、最小限の特権の概念を使用することをお勧めします。 Defender for Endpoint は、Azure Active Directory内の組み込みロールを利用します。 Microsoft では、 [使用可能なさまざまなロールを確認](/azure/active-directory/roles/permissions-reference) し、このアプリケーションの各ペルソナのニーズを解決するための適切なロールを選択することをお勧めします。 デプロイが完了したら、一部のロールを一時的に適用し、削除する必要がある場合があります。

<br>

****

|Personas|役割|Azure AD ロール (必要に応じて)|割り当て対象|
|---|---|---|---|
|セキュリティ管理者||||
|セキュリティ アナリスト||||
|エンドポイント管理者||||
|インフラストラクチャ管理者||||
|ビジネス所有者/利害関係者||||
|

Microsoft では[、Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)を使用してロールを管理し、ディレクトリアクセス許可を持つユーザーに追加の監査、制御、アクセス レビューを提供することをお勧めします。

Defender for Endpoint では、アクセス許可を管理する 2 つの方法がサポートされています。

- **基本的なアクセス許可管理**: アクセス許可をフル アクセスまたは読み取り専用に設定します。 Azure Active Directoryのグローバル管理者ロールまたはセキュリティ管理者ロールを持つユーザーは、フル アクセス権を持ちます。 セキュリティ リーダー ロールには読み取り専用アクセス権があり、マシン/デバイス インベントリを表示するためのアクセス権は付与されません。

- **ロールベースのアクセス制御 (RBAC)**: ロールを定義し、Azure ADユーザー グループをロールに割り当て、ユーザー グループにデバイス グループへのアクセス権を付与することで、きめ細かなアクセス許可を設定します。 詳細はこちら。 [ロールベースのアクセス制御を使用したポータル アクセスの管理に関する](rbac.md)ページを参照してください。

ビジネス上の正当な理由があるユーザーのみが Defender for Endpoint にアクセスできるように、RBAC を利用することをお勧めします。

アクセス許可ガイドラインの詳細については、「ロールを[作成し、Azure Active Directory グループにロールを割り当てる](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)」を参照してください。

次の表の例は、環境に必要な RBAC 構造を決定するのに役立つ、環境内のサイバー防御運用センターの構造を特定するのに役立ちます。

<br>

****

|階層|説明|必要なアクセス許可|
|---|---|---|
|階層 1|**ローカル セキュリティ運用チーム / IT チーム** <p> このチームは通常、位置情報に含まれるアラートをトリアージして調査し、アクティブな修復が必要な場合は階層 2 にエスカレートします。||
|階層 2|**地域のセキュリティ運用チーム** <p> このチームは、リージョンのすべてのデバイスを表示し、修復アクションを実行できます。|データを表示|
|階層 3|**グローバル セキュリティ運用チーム** <p> このチームは、セキュリティの専門家で構成され、ポータルからのすべてのアクションを表示および実行する権限を持っています。|データを表示 <p> アラートの調査 アクティブな修復アクション <p> アラートの調査 アクティブな修復アクション <p> ポータル システム設定を管理する <p> セキュリティ設定の管理|
||||

## <a name="adoption-order"></a>導入順序

多くの場合、組織には既存のエンドポイント セキュリティ製品が用意されています。 最小限のすべての組織は、ウイルス対策ソリューションである必要があります。 しかし、場合によっては、組織が既にEDRソリューションを移植している場合もあります。

以前は、アプリケーション層とインフラストラクチャの依存関係への緊密なフックのため、以前は時間のかかるセキュリティ ソリューションを置き換えるのが困難です。 ただし、Defender for Endpoint はオペレーティング システムに組み込まれているので、サード パーティのソリューションを置き換えるのが簡単になりました。

使用する Defender for Endpoint のコンポーネントを選択し、適用されていないコンポーネントを削除します。 次の表は、エンドポイント セキュリティ スイートを有効にする方法について Microsoft が推奨する順序を示しています。

<br>

****

|コンポーネント|説明|導入順序ランク|
|---|---|---|
|エンドポイント検出&応答 (EDR)|Defender for Endpoint エンドポイントでの検出と対応機能は、ほぼリアルタイムで実行可能な高度な攻撃検出を提供します。 セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。 <p> [詳細情報](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)|1|
|脅威&脆弱性管理 (TVM)|脅威&脆弱性管理は、Microsoft Defender for Endpointのコンポーネントであり、セキュリティ管理者とセキュリティ運用チームの両方に、次のような一意の価値を提供します。 <ul><li>エンドポイントの脆弱性に関連したリアルタイムのエンドポイント検出と応答（EDR）の分析</li><li>インシデント調査中の非常に貴重なデバイスの脆弱性コンテキスト</li><li>Microsoft Intuneと Microsoft System Center Configuration Managerによる組み込みの修復プロセス</li></ul> <p> [詳細情報](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845) を参照してください。|2|
|次世代保護 (NGP)|Microsoft Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、およびサーバーに次世代の保護を提供する組み込みのマルウェア対策ソリューションです。 Microsoft Defender ウイルス対策には、次のものが含まれます。 <ul><li>新たに出現する脅威をほぼ瞬時に検出し、ブロックするためのクラウドによる保護。 機械学習やインテリジェント セキュリティ グラフに加えて、クラウドによる保護は Microsoft Defender ウイルス対策を強化する次世代テクノロジの一部です。</li><li>高度なファイルとプロセス動作の監視とその他のヒューリスティック ("リアルタイム保護" とも呼ばれます) を使用した常時オン スキャン。</li><li>機械学習、人間と自動化されたビッグ データ分析、詳細な脅威対策の研究に基づく専用の保護更新。</li></ul> <p> [詳細情報](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) を参照してください。|3|
|攻撃面の縮小 (ASR)|Microsoft Defender for Endpointの攻撃面の縮小機能は、組織内のデバイスとアプリケーションを新しい脅威や新しい脅威から保護するのに役立ちます。 <br> [詳細情報](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)|4|
|自動調査&修復 (AIR)|Microsoft Defender for Endpointでは、自動調査を使用して、個別に調査する必要があるアラートの量を大幅に減らします。 自動調査機能は、さまざまな検査アルゴリズムと、アナリスト (プレイブックなど) によって使用されるプロセスを利用して、アラートを調べ、侵害を解決するための直ちに修復アクションを実行します。 これにより、アラート量が大幅に削減され、セキュリティ運用の専門家は、より高度な脅威やその他の価値の高い業務に集中できるようになります。 <p> [詳細情報](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)|該当なし|
|Microsoft 脅威エキスパート (MTE)|Microsoft 脅威エキスパートは、セキュリティ オペレーション センター (SOC) に専門家レベルの監視と分析を提供するマネージド ハンティング サービスであり、固有の環境で重大な脅威が見逃されないように支援します。 <p> [詳細情報](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)|該当なし|

## <a name="next-step"></a>次の手順

![フェーズ 2: セットアップ。](images/setup.png) <br> [フェーズ 2: セットアップ](production-deployment.md)

Microsoft Defender for Endpointデプロイを設定します。

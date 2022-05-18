---
title: Microsoft 365 ゼロ トラスト展開プラン
f1.keywords:
- deploy zero trust
- zero trust strategy
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
description: Microsoft 365 ゼロ トラストセキュリティを環境にデプロイして、脅威から保護し、機密データを保護する方法について説明します。
ms.topic: tutorial
ms.prod: m365-security
ms.technology: m365d
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365solution-zerotrust
- m365solution-overview
- M365-security-compliance
ms.openlocfilehash: 2f8fe053d0ffb6d453029ab3f7fee17846661b6d
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65469275"
---
# <a name="microsoft-365-zero-trust-deployment-plan"></a>Microsoft 365 ゼロ トラスト展開プラン

この記事では、Microsoft 365を使用 **してゼロ トラストセキュリティを** 構築するための展開計画について説明します。 ゼロ トラストは、侵害を想定し、制御されていないネットワークから送信されたかのように各要求を検証する新しいセキュリティ モデルです。 要求の発信元やアクセスするリソースに関係なく、ゼロ トラスト モデルは"信頼せず、常に検証する" ことを教えています。

この記事は、このポスターと共に使用してください。

| アイテム | 説明 |
|:-----|:-----|
|[![Microsoft 365 ゼロ トラスト展開計画の図。](../media/solutions-architecture-center/m365-zero-trust-deployment-plan-thumb.png) ](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf) <br/> [PDF](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf) \| [Visio](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.vsdx) <br/> 更新日:2022 年 3 月 | **関連するソリューション ガイド** <br/> <ul><li>[Microsoft 365用の ID インフラストラクチャをデプロイする](/microsoft-365/enterprise/deploy-identity-solution-overview)</li><li>[推奨される ID とデバイス アクセスの構成](../security/office-365-security/microsoft-365-policies-configurations.md)</li><li>[Intune でデバイスを管理する](../solutions/manage-devices-with-intune-overview.md)</li><li>[Microsoft 365 Defender の評価とパイロット](../security/defender/eval-overview.md)</li><li>[Microsoft の情報保護ソリューションの展開](../compliance/information-protection-solution.md)</li><li>[Microsoft 365を使用してデータプライバシー規制の情報保護を展開する](../solutions/information-protection-deploy.md)</li></ul>

## <a name="zero-trust-security-architecture"></a>ゼロ トラストセキュリティ アーキテクチャ

ゼロ トラストアプローチは、デジタル資産全体に及び、統合されたセキュリティ哲学とエンド ツー エンド戦略として機能します。

この図は、ゼロ トラストに貢献する主な要素の表現を示しています。

:::image type="content" source="../media/zero-trust/zero-trust-architecture.png" alt-text="ゼロ トラストセキュリティ アーキテクチャ" lightbox="../media/zero-trust/zero-trust-architecture.png":::

この図について:

- セキュリティ ポリシーの適用は、ゼロ トラスト アーキテクチャの中心にあります。 これには、ユーザー アカウントのリスク、デバイスの状態、および設定したその他の条件とポリシーを考慮した条件付きアクセスを使用した多要素認証が含まれます。
- ID、デバイス、データ、アプリ、ネットワーク、その他のインフラストラクチャ コンポーネントはすべて、適切なセキュリティで構成されます。 これらの各コンポーネントに対して構成されるポリシーは、全体的なゼロ トラスト戦略と調整されます。 たとえば、デバイス ポリシーは正常なデバイスの条件を決定し、条件付きアクセス ポリシーでは特定のアプリやデータへのアクセスに正常なデバイスが必要です。
- 脅威の保護とインテリジェンスは、環境を監視し、現在のリスクを解決し、攻撃を修復するための自動アクションを実行します。

ゼロ トラストの詳細については、Microsoft の [_**ゼロ トラスト ガイダンス センター**_](/security/zero-trust)を参照してください。

<!---
For more information about this architecture, including deployment objectives for your entire digital estate, see [Zero Trust Rapid Modernization Plan (RaMP)](https://review.docs.microsoft.com/security/zero-trust/zero-trust-ramp-overview?branch=zt-content-prototype).
-->



## <a name="deploying-zero-trust-for-microsoft-365"></a>Microsoft 365のゼロ トラストのデプロイ

Microsoft 365は、環境へのゼロ トラストの構築に役立つ多くのセキュリティおよび情報保護機能を備えて意図的に構築されています。 組織が使用する他の SaaS アプリやこれらのアプリ内のデータへのアクセスを保護するために、機能の多くを拡張できます。

この図は、ゼロ トラスト機能をデプロイする作業を表しています。 この作業は、一緒に構成できる作業単位に分割され、下から始まり、上に作業して、前提条件の作業が完了していることを確認します。

:::image type="content" source="../media/zero-trust/m365-zero-trust-deployment-stack.png" alt-text="Microsoft 365 ゼロ トラストデプロイ スタック" lightbox="../media/zero-trust/m365-zero-trust-deployment-stack.png":::

この図について:

- ゼロ トラストは、ID とデバイス保護の基礎から始まります。
- 脅威保護機能は、セキュリティ上の脅威をリアルタイムで監視および修復するために、この基盤の上に構築されています。
- 情報保護とガバナンスは、特定の種類のデータを対象とした高度な制御を提供し、最も貴重な情報を保護し、個人情報の保護を含むコンプライアンス基準を遵守するのに役立ちます。


この記事では、クラウド ID が既に構成されていることを前提としています。 この目的に関するガイダンスが必要な場合は、「[**Microsoft 365用の ID インフラストラクチャをデプロイする」を参照してください**](/microsoft-365/enterprise/deploy-identity-solution-overview)。

## <a name="step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies"></a>手順 1。 ゼロ トラスト ID とデバイス アクセス保護の構成 - 開始点ポリシー

最初の手順は、ID とデバイス アクセス保護を構成してゼロ トラスト基盤を構築することです。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-1b.png" alt-text="ゼロ トラスト ID とデバイス アクセス保護を構成するプロセス" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-1b.png":::

これを実現するための規範的なガイダンスについては、[**_id とデバイス アクセス保護のゼロ トラスト_**](office-365-security/microsoft-365-policies-configurations.md)に移動します。 この一連の記事では、一連の ID とデバイス アクセスの前提条件構成と、Azure Active Directory (Azure AD) 条件付きアクセス、Microsoft Intune、およびその他のポリシーのセットについて説明し、Microsoft 365 エンタープライズ クラウド アプリとサービス、その他の SaaS サービス、および Azure AD アプリケーション プロキシで公開されたオンプレミス アプリケーションの場合。

|Includes|前提条件|含まれていない|
|---------|---------|---------|
|3 層の保護に推奨される ID ポリシーとデバイス アクセス ポリシー: <ul><li>開始点</li><li>Enterprise (推奨)</li><li>専門</li></ul> <br> 次に関するその他の推奨事項: <ul><li>外部ユーザー (ゲスト)</li><li>Microsoft Teams</li><li>SharePoint Online</li><li>Microsoft Defender for Cloud Apps</lu></ul>|Microsoft E3 または E5 <br><br> 次のいずれかのモードでAzure Active Directoryします。 <ul><li>クラウド専用</li><li>パスワード ハッシュ同期 (PHS) 認証を使用したハイブリッド</li><li>パススルー認証 (PTA) を使用したハイブリッド</li><li>フェデレーション</li></ul>|管理対象デバイスを必要とするポリシーのデバイス登録。 [手順 2. を参照してください。デバイスを登録するためのIntuneを使用してエンドポイントを管理](#step-2-manage-endpoints-with-intune)する|

まず、開始点レベルを実装します。 これらのポリシーでは、デバイスを管理に登録する必要はありません。

:::image type="content" source="../media/zero-trust/identity-access-starting-point-tier.png" alt-text="ゼロ トラスト ID ポリシーとデバイス アクセス ポリシー ( 開始点レベル)" lightbox="../media/zero-trust/identity-access-starting-point-tier.png":::

## <a name="step-2-manage-endpoints-with-intune"></a>手順 2。 Intuneを使用してエンドポイントを管理する

次に、デバイスを管理に登録し、より高度な制御でデバイスの保護を開始します。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-2.png" alt-text="Intune要素を使用したエンドポイントの管理" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-2.png":::

これを実現するための規範的なガイダンスについては [**_、Intuneを使用したデバイスの管理_**](../solutions/manage-devices-with-intune-overview.md)に関するページを参照してください。

|Includes|前提条件|含まれていない|
|---------|---------|---------|
|Intuneを使用してデバイスを登録します。 <ul><li>企業所有のデバイス。</li><li>Autopilot/automated</li><li>登録</li></ul> <br> ポリシーを構成します。 <ul><li>App Protection ポリシー</li><li>コンプライアンス ポリシー</li><li>デバイス プロファイル ポリシー</li></ul>|Azure AD にエンドポイントを登録する|次のような情報保護機能の構成: <ul><li>機密情報の種類</li><li>ラベル</li><li>DLP ポリシー</li></ul> <br> これらの機能については、 [手順 5. を参照してください。機密データを保護および管理します](#step-5-protect-and-govern-sensitive-data) (この記事の後半)。|

## <a name="step-3-add-zero-trust-identity-and-device-access-protection--enterprise-policies"></a>手順 3. ゼロ トラスト ID とデバイス アクセス保護を追加する — Enterprise ポリシー

デバイスを管理に登録すると、推奨される ゼロ トラスト id ポリシーとデバイス アクセス ポリシーの完全なセットを実装できるようになり、準拠しているデバイスが必要になります。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png" alt-text="デバイス管理を使用したゼロ トラスト ID ポリシーとアクセス ポリシー" lightbox="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png":::

[**_共通 ID ポリシーとデバイス アクセス ポリシー_**](office-365-security/identity-access-policies.md)に戻り、Enterprise 層にポリシーを追加します。

:::image type="content" source="../media/zero-trust/identity-access-enterprise-tier.png" alt-text="ゼロ トラスト ID とアクセス ポリシー — Enterprise (推奨) レベル" lightbox="../media/zero-trust/identity-access-enterprise-tier.png":::

## <a name="step-4-evaluate-pilot-and-deploy-microsoft-365-defender"></a>手順 4. Microsoft 365 Defenderを評価、パイロット、デプロイする

Microsoft 365 Defenderは、エンドポイント、電子メール、アプリケーション、ID など、Microsoft 365環境全体のシグナル、脅威、アラート データを自動的に収集、関連付け、分析する拡張検出および応答 (XDR) ソリューションです。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-defender.png" alt-text="ゼロ トラスト アーキテクチャにMicrosoft 365 Defenderを追加するプロセス" lightbox="../media/zero-trust/m365-zero-trust-architecture-defender.png":::

Microsoft 365 Defender コンポーネントの [**_パイロットと_**](defender/eval-overview.md)デプロイに関する組織的なガイドについては、「Microsoft 365 Defenderの評価とパイロット」に移動します。

|Includes|前提条件|含まれていない|
|---------|---------|---------|
|すべてのコンポーネントの評価環境とパイロット環境を設定します。 <ul><li>Defender for Identity</li><li>Defender for Office 365</li><li>Defender for Endpoint</li><li>Microsoft Defender for Cloud Apps</li></ul> <br> 脅威から保護する <br><br> 脅威の調査と対応|Microsoft 365 Defenderの各コンポーネントのアーキテクチャ要件については、ガイダンスを参照してください。| このソリューション ガイドには Azure AD Identity Protection は含まれていません。 手順 1. に含まれています[。ゼロ トラスト ID とデバイス アクセス保護を構成](#step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies)します。|

## <a name="step-5-protect-and-govern-sensitive-data"></a>手順 5.  機密データの保護と管理

Microsoft Purview 情報保護を実装して、機密情報がどこに存在するか、移動する場所を問わず検出、分類、保護できるようにします。

Microsoft Purview 情報保護機能はMicrosoft Purviewに含まれており、データを把握し、データを保護し、データの損失を防ぐためのツールを提供します。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-info-protect.png" alt-text="ポリシーの適用を通じてデータを保護する情報保護機能" lightbox="../media/zero-trust/m365-zero-trust-architecture-info-protect.png":::

この作業は、この記事の前に説明したデプロイ スタックの先頭に表示されますが、この作業はいつでも開始できます。

Microsoft Purview 情報保護は、特定のビジネス目標を達成するために使用できるフレームワーク、プロセス、および機能を提供します。

![Microsoft Purview Information Protection](../media/zero-trust/mip-solution-overview.png)

情報保護を計画およびデプロイする方法の詳細については、「[**_Microsoft Purview 情報保護 ソリューションのデプロイ_**](../compliance/information-protection-solution.md)」を参照してください。 

データ プライバシー規制の情報保護を展開する場合、このソリューション ガイドでは、プロセス全体に推奨されるフレームワークとして、Microsoft 365を使用して [**_データプライバシー規制の情報保護を展開_**](../solutions/information-protection-deploy.md)します。

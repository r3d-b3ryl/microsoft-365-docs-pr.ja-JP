---
title: アーキテクチャの要件とMicrosoft Defender for Cloud Appsの構造を確認する
description: Microsoft Defender for Cloud Apps技術図では、パイロット環境の構築に役立つMicrosoft 365 Defenderのアーキテクチャについて説明しています。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: e012ee5c94a37456a67dc5624e2aae0a2a460548
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67473812"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Appsのアーキテクチャ要件と主要な概念を確認する


**適用対象:**

- Microsoft 365 Defender

この記事は、Microsoft 365 Defenderと共にMicrosoft Defender for Cloud Appsの評価環境を設定する[手順 1/3](eval-defender-mcas-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-identity-overview.md)関する記事を参照してください。

Microsoft Defender for Cloud Appsを有効にする前に、アーキテクチャを理解し、要件を満たすことができることを確認してください。 

## <a name="understand-the-architecture"></a>アーキテクチャを理解する

Microsoft Defender for Cloud Appsはクラウド アクセス セキュリティ ブローカー (CASB) です。 CASB は、エンタープライズ ユーザーと使用するクラウド リソースの間のアクセスをリアルタイムで仲介するゲートキーパーとして機能します。ユーザーが配置されている場所と、使用しているデバイスに関係なく。 Microsoft Defender for Cloud Appsは、Microsoft 365 Defenderを含む Microsoft セキュリティ機能とネイティブに統合されます。

Defender for Cloud Apps を使用しない場合、組織で使用されるクラウド アプリは、図に示すように管理されておらず、保護されていません。

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-a.png" alt-text="Microsoft Defender for Cloud Appsのアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-a.png":::

この図について:
- 組織によるクラウド アプリの使用は監視されておらず、保護されていません。 
- この使用は、マネージド組織内で達成される保護の範囲外です。 

#### <a name="discovering-cloud-apps"></a>クラウド アプリの検出

クラウド アプリの使用を管理する最初の手順は、組織で使用されているクラウド アプリを検出することです。 次の図は、Defender for Cloud Apps でのクラウド検出のしくみを示しています。

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-b.png" alt-text="クラウド検出でのMicrosoft Defender for Cloud Appsのアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-b.png":::


この図では、ネットワーク トラフィックを監視し、組織で使用されているクラウド アプリを検出するために使用できる 2 つの方法があります。
- A. Cloud App Discovery は、ネイティブにMicrosoft Defender for Endpointと統合されます。 Defender for Endpoint は、IT マネージド Windows 10およびWindows 11 デバイスからアクセスされるクラウド アプリとサービスを報告します。 
- B. ネットワークに接続されているすべてのデバイスのカバレッジについては、Defender for Cloud Apps ログ コレクターがファイアウォールやその他のプロキシにインストールされ、エンドポイントからデータが収集されます。 このデータは、分析のために Defender for Cloud Apps に送信されます。

#### <a name="managing-cloud-apps"></a>クラウド アプリの管理

クラウド アプリを検出し、組織でこれらのアプリがどのように使用されているかを分析したら、選択したクラウド アプリの管理を開始できます。 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-c.png" alt-text="クラウド アプリの管理中のMicrosoft Defender for Cloud Appsのアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-c.png":::

この図について:
- 一部のアプリでは、使用が認められます。 この承認は、アプリを管理し始める簡単な方法です。
- アプリコネクタを使用してアプリを接続することで、より高い可視性と制御を有効にすることができます。 アプリ コネクタは、アプリ プロバイダーの API を使用します。


#### <a name="applying-session-controls-to-cloud-apps"></a>クラウド アプリへのセッション コントロールの適用

Microsoft Defender for Cloud Appsはリバース プロキシとして機能し、認可されたクラウド アプリへのプロキシ アクセスを提供します。 このプロビジョニングにより、Defender for Cloud Apps は、構成したセッション 制御を適用できます。 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-d.png" alt-text="Microsoft Defender for Cloud Appsのアーキテクチャ - プロキシ アクセス セッション制御" lightbox="../../media/defender/m365-defender-mcas-architecture-d.png":::

この図について:
- 組織内のユーザーとデバイスから承認されたクラウド アプリへのアクセスは、Defender for Cloud Apps 経由でルーティングされます。
- このプロキシ アクセスを使用すると、セッション制御を適用できます。
- 承認されていないクラウド アプリや明示的に承認されていないクラウド アプリは影響を受けられません。

セッション コントロールを使用すると、組織でクラウド アプリを使用する方法にパラメーターを適用できます。 たとえば、組織が Salesforce を使用している場合は、管理対象デバイスのみが Salesforce で組織のデータにアクセスできるようにするセッション ポリシーを構成できます。 より簡単な例として、より厳格なポリシーを適用する前に、このトラフィックのリスクを分析できるように、管理されていないデバイスからのトラフィックを監視するポリシーを構成できます。

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>Azure AD と条件付きアクセス アプリ制御の統合

多要素認証やその他の条件付きアクセス ポリシーを適用するために、既に Azure AD テナントに SaaS アプリを追加している可能性があります。 Microsoft Defender for Cloud Apps Azure AD とネイティブに統合されます。 必要なのは、Defender for Cloud Apps で条件付きアクセス アプリ制御を使用するように Azure AD でポリシーを構成することです。 これにより、これらのマネージド SaaS アプリのネットワーク トラフィックが Defender for Cloud Apps をプロキシとしてルーティングされ、Defender for Cloud Apps でこのトラフィックを監視し、セッション制御を適用できます。 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-e.png" alt-text="Microsoft Defender for Cloud Appsのアーキテクチャ - SaaS アプリ" lightbox="../../media/defender/m365-defender-mcas-architecture-e.png":::

この図について:
- SaaS アプリは、Azure AD テナントと統合されています。 この統合により、Azure AD では、多要素認証を含む条件付きアクセス ポリシーを適用できます。
- SaaS アプリのトラフィックを Defender for Cloud Apps に転送するためのポリシーが Azure Active Directory に追加されます。 このポリシーでは、このポリシーを適用する SaaS アプリを指定します。 そのため、Azure AD がこれらの SaaS アプリに適用される条件付きアクセス ポリシーを適用した後、Azure AD は Defender for Cloud Apps を介してセッション トラフィックを送信 (プロキシ) します。
- Defender for Cloud Apps は、このトラフィックを監視し、管理者によって構成されたすべてのセッション制御ポリシーを適用します。 

Azure AD に追加されていない Defender for Cloud Apps を使用して、クラウド アプリを検出し、承認した可能性があります。 条件付きアクセス アプリ制御を利用するには、これらのクラウド アプリを Azure AD テナントと条件付きアクセス規則の範囲に追加します。

#### <a name="protecting-your-organization-from-hackers"></a>ハッカーから組織を保護する

Defender for Cloud Apps は、独自に強力な保護を提供します。 ただし、Microsoft 365 Defenderの他の機能と組み合わせると、Defender for Cloud Apps は、(一緒に) 攻撃を停止するのに役立つ共有シグナルにデータを提供します。

概要からこのMicrosoft 365 Defender評価ガイドとパイロット ガイドまで、この図を繰り返す価値があります。 

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="Microsoft 365 Defenderが脅威の連鎖を阻止する方法" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

この図の右側に注目すると、Microsoft Defender for Cloud Appsは、不可能な移動、資格情報アクセス、異常なダウンロード、ファイル共有、メール転送アクティビティなどの異常な動作に気付き、これらの動作をセキュリティ チームに報告します。 そのため、Defender for Cloud Apps は、ハッカーによる横移動や機密データの流出を防ぐのに役立ちます。 Microsoft 356 Defender for Cloud は、すべてのコンポーネントからのシグナルを関連付けて、完全な攻撃ストーリーを提供します。

## <a name="understand-key-concepts"></a>主要な概念を理解する

次の表では、Microsoft Defender for Cloud Appsを評価、構成、デプロイするときに理解するために重要な重要な概念を示します。


|概念  |説明 |詳細情報  |
|---------|---------|---------|
| Defender for Cloud Apps ダッシュボード | 組織に関する最も重要な情報の概要と、詳細な調査へのリンクを示します。        | [ダッシュボードの操作 ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| アプリの条件付きアクセスを制御する    | ID プロバイダー (IdP) と統合して Azure AD の条件付きアクセス ポリシーを付与し、セッション制御を選択的に適用するリバース プロキシ アーキテクチャ。        |  [条件付きアクセス アプリ制御Microsoft Defender for Cloud Apps使用してアプリを保護する](/cloud-app-security/proxy-intro-aad)       |
|  Cloud App Catalog   | クラウド アプリ カタログは、80 を超えるリスク要因に基づいてランク付けされ、スコア付けされた 16,000 を超えるクラウド アプリの Microsoft カタログに対する全体像を提供します。    |  [アプリのリスク スコアの操作](/cloud-app-security/risk-score)       |
| Cloud Discovery ダッシュボード    | Cloud Discovery はトラフィック ログを分析し、組織でクラウド アプリがどのように使用されているかについてのより多くの分析情報を提供し、アラートとリスク レベルを提供するように設計されています。     |  [検出されたアプリの操作   ](/cloud-app-security/discovered-apps)    |
|接続済みアプリ |Defender for Cloud Apps は、クラウド間統合、API コネクタ、条件付きアプリ アクセス制御を使用したリアルタイムのアクセスとセッション制御を使用して、接続されたアプリのエンドツーエンドの保護を提供します。 |[接続されているアプリの保護](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>アーキテクチャ要件を確認する

### <a name="discovering-cloud-apps"></a>クラウド アプリの検出

環境で使用されているクラウド アプリを検出するには、次の方法のいずれかまたは両方を実装できます。

- Microsoft Defender for Endpointと統合することで、Cloud Discovery を使用して迅速に起動して実行します。 このネイティブ統合を使用すると、Windows 11およびWindows 10 デバイス間のクラウド トラフィックに関するデータの収集をすぐに開始できます。ネットワークのオンとオフを切り替えます。
- ネットワークに接続されているすべてのデバイスからアクセスされたすべてのクラウド アプリを検出するには、ファイアウォールやその他のプロキシに Defender for Cloud Apps ログ コレクターをデプロイします。 このデプロイは、エンドポイントからデータを収集し、分析のために Defender for Cloud Apps に送信するのに役立ちます。 Defender for Cloud Apps は、より多くの機能を実現するために、一部のサードパーティ プロキシとネイティブに統合されています。

これらのオプションは [、手順 2 に含まれています。評価環境を有効にします](eval-defender-mcas-enable-eval.md)。 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>Azure AD 条件付きアクセス ポリシーをクラウド アプリに適用する

条件付きアクセス アプリ制御 (クラウド アプリに条件付きアクセス ポリシーを適用する機能) には、Azure AD との統合が必要です。 この統合は、Defender for Cloud Apps の使用を開始するための要件ではありません。 これは、パイロット フェーズ (手順 3) の間に試してみることをお勧めする[手順です。パイロット Microsoft Defender for Cloud Apps](eval-defender-mcas-pilot.md)。

## <a name="siem-integration"></a>SIEM 統合

Microsoft Defender for Cloud Appsを汎用 SIEM サーバーまたは Microsoft Sentinel と統合して、接続されたアプリからのアラートとアクティビティを一元的に監視できます。 

さらに、Microsoft Sentinel には、Microsoft Sentinel とのより深い統合を提供するMicrosoft Defender for Cloud Apps コネクタが含まれています。 この配置により、クラウド アプリの可視性を得るだけでなく、高度な分析を取得してサイバー脅威を特定して対処し、データの移動方法を制御することもできます。

- [一般的な SIEM 統合](/cloud-app-security/siem)
- [Defender for Cloud Apps から Microsoft Sentinel にアラートと Cloud Discovery ログをストリーミングする](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>次の手順

手順 2/3: [Microsoft Defender for Cloud Appsの評価環境を有効にする](eval-defender-mcas-enable-eval.md)

[Microsoft Defender for Cloud Appsの評価](eval-defender-mcas-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る

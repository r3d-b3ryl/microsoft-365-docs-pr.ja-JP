---
title: Microsoft Defender for Cloud Apps のアーキテクチャ要件と構造を確認する
description: Microsoft Defender for Cloud Apps の技術図では、パイロット環境の構築に役立つMicrosoft 365 Defenderのアーキテクチャについて説明します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6547c1b269ede9385b384ca18fe6f2ca34d35109
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500323"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps のアーキテクチャ要件と主な概念を確認する


**適用対象:**

- Microsoft 365 Defender

この記事では、Microsoft Defender for Cloud Apps の評価環境を設定するプロセスの手順 [1/3](eval-defender-mcas-overview.md) と、Microsoft Defender for Cloud Apps と共に、Microsoft 365 Defender。 このプロセスの詳細については、概要の記事を [参照してください](eval-defender-identity-overview.md)。

Microsoft Defender for Cloud Apps を有効にする前に、アーキテクチャを理解し、要件を満たしていることを確認してください。 

## <a name="understand-the-architecture"></a>アーキテクチャを理解する

Microsoft Defender for Cloud Apps は、クラウド アクセス セキュリティ ブローカー (CASB) です。 CASB は、エンタープライズ ユーザーと使用するクラウド リソースの間で、ユーザーがどこにいても、使用しているデバイスに関係なく、リアルタイムでアクセスを仲介するゲートキーパーとして機能します。 Microsoft Defender for Cloud Apps は、Microsoft のセキュリティ機能とネイティブに統合されます(Microsoft 365 Defender。

Defender for Cloud Apps を使用しない場合、組織で使用されているクラウド アプリは、図に示す通り管理および保護されません。

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-a.png" alt-text="Microsoft Defender for Cloud Apps のアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-a.png":::

この図について:
- 組織によるクラウド アプリの使用は、管理され保護されません。 
- この使用は、管理組織内で達成される保護の外に含まれる。 

#### <a name="discovering-cloud-apps"></a>クラウド アプリの検出

クラウド アプリの使用を管理する最初の手順は、組織で使用されているクラウド アプリを検出する方法です。 次の図は、クラウド検出が Defender for Cloud Apps でどのように機能するのか示しています。

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-b.png" alt-text="クラウド検出での Microsoft Defender for Cloud Apps のアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-b.png":::


この図では、ネットワーク トラフィックを監視し、組織で使用されているクラウド アプリを検出するために使用できる 2 つの方法があります。
- A. クラウド アプリの検出は、Microsoft Defender for Endpoint とネイティブに統合されます。 Defender for Endpoint は、11 台のデバイスから IT 管理されたデバイスからアクセスされるクラウド アプリとサービスWindows 10レポートWindowsレポートします。 
- B. ネットワークに接続されているすべてのデバイスでカバレッジを行う場合は、Defender for Cloud Apps ログ コレクターがファイアウォールや他のプロキシにインストールされ、エンドポイントからデータを収集します。 このデータは、分析のために Defender for Cloud Apps に送信されます。

#### <a name="managing-cloud-apps"></a>クラウド アプリの管理

クラウド アプリを検出し、組織でこれらのアプリがどのように使用されるのか分析した後、選択したクラウド アプリの管理を開始できます。 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-c.png" alt-text="クラウド アプリの管理中の Microsoft Defender for Cloud Apps のアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-c.png":::

この図について:
- 一部のアプリは使用が許可されています。 この制裁は、アプリの管理を始める簡単な方法です。
- アプリをアプリ コネクタに接続することで、より大きな可視性と制御を有効にできます。 アプリ コネクタは、アプリ プロバイダーの API を使用します。


#### <a name="applying-session-controls-to-cloud-apps"></a>クラウド アプリへのセッション コントロールの適用

Microsoft Defender for Cloud Apps はリバース プロキシとして機能し、認可されたクラウド アプリへのプロキシ アクセスを提供します。 このプロビジョニングにより、Defender for Cloud Apps は、構成したセッション コントロールを適用できます。 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-d.png" alt-text="Microsoft Defender for Cloud Apps - プロキシ アクセス セッション制御のアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-d.png":::

この図について:
- 組織内のユーザーおよびデバイスから認可されたクラウド アプリへのアクセスは、Defender for Cloud Apps を介してルーティングされます。
- このプロキシ アクセスでは、セッション コントロールを適用できます。
- 許可されていない、または明示的に認可されていないクラウド アプリは影響を受け取る必要があります。

セッション コントロールを使用すると、組織でのクラウド アプリの使用方法にパラメーターを適用できます。 たとえば、組織が Salesforce を使用している場合は、管理対象デバイスだけが Salesforce で組織のデータにアクセスできるセッション ポリシーを構成できます。 より簡単な例として、管理されていないデバイスからのトラフィックを監視するポリシーを構成して、より厳しいポリシーを適用する前に、このトラフィックのリスクを分析できます。

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>条件付きアクセス アプリAzure ADと統合する

多要素認証や他の条件付きアクセス ポリシーを適用するために、Azure ADに SaaS アプリが既に追加されている場合があります。 Microsoft Defender for Cloud Apps は、クラウド アプリとネイティブAzure AD。 クラウド アプリの Defender で条件付きアクセス Azure ADを使用するポリシーを構成する必要があります。 これにより、これらの管理対象 SaaS アプリのネットワーク トラフィックが Defender for Cloud Apps をプロキシとしてルーティングされ、Defender for Cloud Apps は、このトラフィックを監視し、セッションコントロールを適用できます。 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-e.png" alt-text="Microsoft Defender for Cloud Apps - SaaS アプリのアーキテクチャ" lightbox="../../media/defender/m365-defender-mcas-architecture-e.png":::

この図について:
- SaaS アプリは、クラウド テナントAzure ADされます。 この統合により、Azure AD多要素認証を含む条件付きアクセス ポリシーを適用できます。
- SaaS アプリのトラフィックAzure Active Directory Defender for Cloud Apps に送信するポリシーがポリシーに追加されます。 ポリシーは、このポリシーを適用する SaaS アプリを指定します。 したがって、Azure ADこれらの SaaS アプリに適用される条件付きアクセス ポリシーを適用した後、Azure AD は Defender for Cloud Apps を介してセッション トラフィックを送信 (プロキシ) します。
- Defender for Cloud Apps は、このトラフィックを監視し、管理者が構成したセッション制御ポリシーを適用します。 

Defender for Cloud Apps を使用して、クラウド アプリに追加されていないクラウド アプリを検出してAzure AD。 条件付きアクセス アプリ制御を利用するには、これらのクラウド アプリを Azure AD テナントと条件付きアクセス ルールの範囲に追加します。

#### <a name="protecting-your-organization-from-hackers"></a>ハッカーから組織を保護する

Defender for Cloud Apps は、独自に強力な保護を提供します。 ただし、Defender for Cloud Apps は、Microsoft 365 Defenderの他の機能と組み合わせると、共有信号にデータを提供し、(一緒に) 攻撃の停止に役立ちます。

この図は、概要からこの評価とパイロット ガイドMicrosoft 365 Defender繰り返す価値があります。 

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="一Microsoft 365 Defenderを停止する方法" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

この図の右側に焦点を当て、Microsoft Defender for Cloud Apps は、不可能な移動、資格情報アクセス、異常なダウンロード、ファイル共有、メール転送アクティビティのような異常な動作に気付き、これらの動作をセキュリティ チームに報告します。 したがって、Defender for Cloud Apps は、ハッカーによる横方向の動きや機密データの侵入を防ぐのに役立ちます。 Microsoft 356 Defender for Cloud は、すべてのコンポーネントからの信号を関連付け、完全な攻撃ストーリーを提供します。

## <a name="understand-key-concepts"></a>主要な概念を理解する

次の表では、Microsoft Defender for Cloud Apps の評価、構成、展開を行う際に重要な重要な概念を示しています。


|概念  |説明 |詳細情報  |
|---------|---------|---------|
| Defender for Cloud Apps Dashboard | 組織に関する最も重要な情報の概要を示し、より深い調査へのリンクを提供します。        | [ダッシュボードの操作 ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| アプリの条件付きアクセスを制御する    | Id プロバイダー (IdP) と統合して、条件付きアクセス ポリシーを提供し、Azure ADを選択的に適用するリバース プロキシ アーキテクチャ。        |  [Microsoft Defender for Cloud Apps 条件付きアクセス アプリ制御でアプリを保護する](/cloud-app-security/proxy-intro-aad)       |
|  クラウド アプリ カタログ   | クラウド アプリ カタログを使用すると、80 を超えるリスク要因に基づいてランク付けおよびスコア付けされた 16,000 を超えるクラウド アプリの Microsoft カタログに対する全体像を確認できます。    |  [アプリのリスク スコアの操作](/cloud-app-security/risk-score)       |
| クラウド探索ダッシュボード    | クラウド検出は、トラフィック ログを分析し、組織内でのクラウド アプリの使用方法に関するより多くの洞察を提供し、アラートとリスク レベルを提供するように設計されています。     |  [検出されたアプリの操作   ](/cloud-app-security/discovered-apps)    |
|接続されたアプリ |Defender for Cloud Apps は、条件付きアプリ アクセス制御を使用して、クラウドからクラウドへの統合、API コネクタ、リアルタイムアクセスおよびセッションコントロールを使用して、接続されたアプリに対するエンドツーエンドの保護を提供します。 |[接続されたアプリの保護](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>アーキテクチャ要件を確認する

### <a name="discovering-cloud-apps"></a>クラウド アプリの検出

環境で使用されているクラウド アプリを検出するには、次の方法の 1 つまたは両方を実装できます。

- Microsoft Defender for Endpoint と統合することで、クラウド探索を迅速に実行できます。 このネイティブ統合により、ネットワークのオンとオフを切り替えて、Windows 11 デバイスWindows 10クラウド トラフィックのデータ収集をすぐに開始できます。
- ネットワークに接続されているすべてのデバイスがアクセスしているすべてのクラウド アプリを検出するには、ファイアウォールや他のプロキシに Defender for Cloud Apps ログ コレクターを展開します。 この展開は、エンドポイントからデータを収集し、分析のために Defender for Cloud Apps に送信するのに役立ちます。 Defender for Cloud Apps は、さらに多くの機能を提供するために、一部のサードパーティ プロキシとネイティブに統合されます。

これらのオプションは、手順 [2 に含まれています。評価環境を有効にする](eval-defender-mcas-enable-eval.md)。 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>クラウド Azure ADへの条件付きアクセス ポリシーの適用

条件付きアクセス アプリ制御 (条件付きアクセス ポリシーをクラウド アプリに適用する機能) には、アプリとのAzure AD。 この統合は、Defender for Cloud Apps の使用を開始する場合の要件ではない。 これは、パイロット フェーズである手順 3 の間に試用することを推奨[する手順です。クラウド アプリ用 Microsoft Defender のパイロット。](eval-defender-mcas-pilot.md)

## <a name="siem-integration"></a>SIEM 統合

Microsoft Defender for Cloud Apps を一般的な SIEM サーバーまたは Microsoft Sentinel と統合して、接続されたアプリからのアラートとアクティビティを一元的に監視できます。 

さらに、Microsoft Sentinel には、Microsoft Sentinel とのより深い統合を提供する Microsoft Defender for Cloud Apps コネクタが含まれています。 この配置により、クラウド アプリを可視化できるだけでなく、高度な分析を利用してサイバー脅威を特定して対処し、データの移動方法を制御できます。

- [一般的な SIEM 統合](/cloud-app-security/siem)
- [Defender for Cloud Apps から Microsoft Sentinel にアラートとクラウド探索ログをストリーミングする](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>次の手順

手順 2/3: [Microsoft Defender for Cloud Apps の評価環境を有効にする](eval-defender-mcas-enable-eval.md)

「Microsoft [Defender for Cloud Apps の評価」の概要に戻る](eval-defender-mcas-overview.md)

[評価とパイロット] [の概要に戻Microsoft 365 Defender](eval-overview.md)

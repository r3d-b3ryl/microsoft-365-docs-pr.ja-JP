---
title: CellTrust SL2 プラットフォームから Microsoft 365 にデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: CellTrust SL2 データ コネクタを設定して使用して、モバイル通信データをインポートおよびアーカイブする方法について説明します。
ms.openlocfilehash: 8c31f349f25702e88a260025ef69475f44f96a0e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624711"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365"></a>CellTrust SL2 から Microsoft 365 にデータをアーカイブする

CellTrust SL2 は、モバイル通信データをキャプチャし、主要なアーカイブ テクノロジと統合して、FINRA、HIPAA、FOIA、TCPA などの規制に関する電子探索要件を満たします。 SL2 Data Connector は、モバイル通信アイテムを Microsoft 365 にインポートします。 この記事では、アーカイブに CellTrust SL2 Data Connector を使用して SL2 と Microsoft 365 を統合するプロセスについて説明します。 このプロセスを完了するには、CellTrust SL2 サービスをサブスクライブしており、SL2 アーキテクチャに精通していることを前提としています。 CellTrust SL2 の詳細については、次を参照してください <https://www.celltrust.com>。

Microsoft 365 のユーザー メールボックスにデータをインポートした後、訴訟ホールド、電子情報開示、Microsoft 365 アイテム保持ポリシー、通信コンプライアンスなどの Microsoft Purview 機能を適用できます。 CellTrust SL2 Data Connector を使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>CellTrust SL2 データ コネクタを使用したアーカイブの概要

CellTrust の SL2 プラットフォームは、複数のソースからの通信データをキャプチャします。 SL2 データ ソースは、個人間 (P2P) または Application-to-Person (A2P) です。 この記事で説明するプロセスは、P2P データ ソースのみに関係します。 すべての P2P データ ソースの場合、コラボレーションの少なくとも 1 つの関係者は、SL2 サービスにサブスクライブしている SL2 ユーザーです。 次の概要では、Microsoft 365 で CellTrust SL2 Data Connector を使用するプロセスについて説明します。

![CellTrust SL2 サービスのアーカイブ ワークフロー。](../media/CellTrustSL2ConnectorWorkflow.png)

1. SL2 ユーザーは、Microsoft Azure の SL2 サービスとの間でデータを送受信します。

2. 組織には、CellTrust の SL2 クラウド サービス環境に SL2 ドメインがあります。 ドメインには、1 つ以上の組織単位 (OU) が含まれる場合があります。 SL2 クラウド サービスは、Microsoft Azure プラットフォームの安全性の高い領域にデータを転送し、データが Microsoft Azure 環境から離れることがないようにします。 SL2 プラン (エンタープライズ、SMB、または政府機関) に応じて、ドメインは Microsoft Azure Global または Microsoft Azure Governmentでホストされます。

3. CellTrust SL2 Data Connector を作成した後、ドメインと OU (SL2 プランに関係なく) は、Microsoft 365 へのデータの送信を開始します。 データ フィードは、データ ソース、OU、またはドメイン自体に基づくレポートをサポートするように構成されています。 その結果、組織では、すべてのデータ ソースを Microsoft 365 にフィードするために必要なコネクタは 1 つだけです。

4. コネクタは、**CellTrust SL2** というタイトルの適切なOffice 365 ライセンスを持つ、マップされた各ユーザーの下にフォルダーを作成します。 このマッピングは、電子メール アドレスを使用して、CellTrust SL2 ユーザーをOffice 365メールボックスに接続します。 CellTrust SL2 のユーザー ID がOffice 365で一致しない場合、ユーザーのデータはアーカイブされません。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- CellTrust SL2 クラウド サービス環境にドメインがあることを確認します。 運用または試用版の SL2 ドメインの取得に関する追加情報については、 [CellTrust にお問い合わせください](https://www.celltrust.com/contact-us/#form)。

- SL2 ドメインの管理者アカウントにアクセスするための資格情報を取得します。

- 手順 1 で CellTrust SL2 データ コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、Microsoft Purview コンプライアンス ポータルの **[データ コネクタ**] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この CellTrust データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-create-a-celltrust-sl2-connector"></a>手順 1: CellTrust SL2 コネクタを作成する

最初の手順は、コンプライアンス ポータルでデータ コネクタを作成することです。

1. 左側のナビゲーション ウィンドウで <https://compliance.microsoft.com> [ **データ コネクタ** ] に移動してクリックします。

2. [ **概要** ] タブで[ **フィルター** ] をクリックし、[ **セルトラスト]** を選択してフィルターを適用します。

   ![CellTrust コネクタを表示するようにフィルターを構成します。](../media/DataConnectorsFilter.png)

3. **CellTrust SL2 (プレビュー)** をクリックします。

4. **CellTrust SL2 (プレビュー)** 製品の説明ページで、[**コネクタの追加**] をクリックします。

5. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

6. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。 入力した名前は、作成後に [ **データ コネクタ** ] ページでコネクタを識別します。

7. **[CellTrust アカウントへのサインイン**] ページで、[**CellTrust へのサインイン**] をクリックします。 新しいブラウザー ウィンドウで **、CellTrust Portal for Microsoft 365** にリダイレクトされます。

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>手順 2: アーカイブするドメインまたは OU を選択する

次の手順では、CellTrust SL2 ドメインの管理者アカウントにサインインし、Microsoft 365 でアーカイブするドメインと OU を選択します。

1. CellTrust **Microsoft 365 コネクタ** ページで、SL2 クラウド サービスで環境を選択してサインイン ページを表示します。

   通常、環境を表す 1 つのオプションが表示されます。 ただし、複数の環境にドメインがある場合は、環境ごとにオプションが表示されます。 選択すると、SL2 ログイン ページにリダイレクトされます。

2. ドメインまたは OU 管理者アカウントの資格情報を使用してサインインします。

   SL2 ドメイン管理者としてサインインすると、ドメインの名前とそのドメイン内の OU が表示されます。 OU がない場合は、ドメインの名前のみが表示されます。 OU 管理者としてログインすると、OU の名前のみが表示されます。

3. アーカイブする部署を有効にします。 ドメインを選択すると、OU は自動的に選択されません。 各 OU を個別に有効にしてアーカイブする必要があります。

   ![OU をアーカイブできるようにします。](../media/EnableCellTrustOUs.png)

4. 選択が完了したら、ブラウザー ウィンドウを閉じて、コンプライアンス ポータルのウィザード ページに戻ります。 数秒後、ウィザードは自動的にユーザーのマッピングの次の手順に進みます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

最後の手順は、ユーザーをマップし、コンプライアンス ポータルでコネクタの設定を完了することです。

1. **[ユーザー マッピング**] ページで、ユーザーの電子メール アドレスが SL2 と Microsoft 365 の両方で同じ場合は、[**自動ユーザー マッピングを有効にする**] を選択します。 それ以外の場合は、ユーザーの SL2 アドレスを Microsoft 365 アドレスにマップする CSV ファイルをアップロードして、電子メール アドレスを手動でユーザーにする必要があります。

2. [ **次へ**] をクリックし、設定を確認し、[ **完了]** をクリックしてコネクタを作成します。

   新しいコネクタが [ **データ コネクタ** ] ページの一覧に追加されます。

## <a name="get-help-from-celltrust"></a>CellTrust からヘルプを受ける

CellTrust SL2 データ コネクタの設定に関するヘルプについては、CellTrust への問い合わせの詳細については、CellTrust [カスタマー サポート ページ](https://www.celltrust.com/contact-us/#support) を参照してください。

## <a name="more-information"></a>詳細情報

- ドメイン管理者は、ドメインまたはそのドメイン内の任意の OU のコネクタを設定できます。 OU 管理者アカウントを使用する場合は、その特定の OU のコネクタのみを設定できます。

- 上記の手順を正常に完了するには、Microsoft 365 E5 ライセンスを割り当て、適切な Microsoft Office 管理者権限を持っている必要があります。

- 新しいコネクタをテストするには、SL2 モバイル アプリまたは SL2 ポータルからテキスト メッセージを送信します。 Microsoft 365 メールボックスに移動し、受信トレイで **CellTrust SL2** フォルダーを開きます。 テキスト メッセージがメールボックスに表示されるまで数分かかる場合があります。

- 多くの法律や規制では、要求された場合に証拠として生成できるように、電子通信を保持する必要があります。 電子情報開示 (電子情報開示) は、電子通信の運用に準拠するために使用されます。 エンタープライズ情報アーカイブ (EIA) ソリューションは、電子情報開示を実行し、アイテム保持ポリシー管理、データ分類、コンテンツ監督などの機能を提供するように設計されています。 Microsoft 365 は、組織に影響を与える規制と標準に準拠するための長期リテンション ソリューションを提供します。

- このドキュメントで使用する *アーカイブ* という用語は、エンタープライズ情報アーカイブ (EIA) ソリューション内で使用されるコンテキストでのアーカイブを指します。 EIA ソリューションには、訴訟、訴訟、監査、および調査のためのドキュメントを生成する電子情報開示機能があります。 ディザスター リカバリーとビジネス継続性に使用されるバックアップと復元のコンテキストでのアーカイブは、このドキュメント内の用語の使用を意図したものではありません。

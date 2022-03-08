---
title: Cisco Jabber データをアーカイブするコネクタをセットアップMicrosoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 17a-4 Cisco Jabber DataParser コネクタをセットアップして使用して、Cisco Jabber データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: 4236b64c805a2524eac080663cdf4fe1e77a595a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329225"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>Cisco Jabber データをアーカイブするコネクタをセットアップする

17a-4 LLC の [Cisco Jabber DataParser](https://www.17a-4.com/jabber-dataparser/) を使用して、Cisco Jabber から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された Cisco Jabber コネクタMicrosoft 365。 Cisco Jabber DataParser コネクタは、Cisco Jabber データを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Cisco Jabber データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Cisco Jabber コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-cisco-jabber-data"></a>Cisco Jabber データのアーカイブの概要

次の概要では、データ コネクタを使用して Cisco Jabber データをアーカイブするプロセスについて説明Microsoft 365。

![17a-4 の Cisco Jabber データのアーカイブ ワークフロー。](../media/CiscoJabberDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して、Cisco Jabber DataParser をセットアップおよび構成します。

2. 定期的に、Cisco Jabber アイテムは DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Cisco Jabber DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. **Cisco Jabber DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーに Cisco Jabber アイテムがインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべての Cisco Jabber アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには、 [17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で Cisco Jabber DataParser コネクタを作成し(手順 3 で完了)、データ コネクタ管理者の役割を割り当てる必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この 17a-4 データ コネクタは、米国政府機関GCC環境Microsoft 365利用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-a-cisco-jabber-dataparser-connector"></a>手順 1: Cisco Jabber DataParser コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、Cisco Jabber データ用の 17a-4 コネクタを作成することです。

1. に移動し<https://compliance.microsoft.com>、[**データ** >  コネクタ **] [Cisco Jabber DataParser] をクリックします**。

2. **[Cisco Jabber DataParser** 製品の説明] ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、Cisco Jabber DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-cisco-jabber-dataparser-connector"></a>手順 2: Cisco Jabber DataParser コネクタを構成する

17a-4 サポートを使用して、Cisco Jabber DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

Cisco Jabber DataParser コネクタは、ユーザーにデータをインポートする前に、ユーザー Microsoft 365メール アドレスに自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-cisco-jabber-dataparser-connector"></a>手順 4: Cisco Jabber DataParser コネクタを監視する

Cisco Jabber DataParser コネクタを作成した後、コネクタの状態を[ネットワーク] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション <https://compliance.microsoft.com> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した Cisco Jabber DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。

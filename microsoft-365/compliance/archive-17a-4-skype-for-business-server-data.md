---
title: コネクタをセットアップして、Skype for Business ServerデータをアーカイブMicrosoft 365
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
description: 17a-4 Skype for Business Server DataParser コネクタをセットアップして使用して、Skype for Business Server データをインポートおよびアーカイブするMicrosoft 365。
ms.openlocfilehash: 8c36b46ad8c49c44b87a11a688e15fcf27d82de0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311831"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-server-data"></a>データをアーカイブするコネクタをSkype for Business Serverする

[17a-4 LLC Skype Server DataParser](https://www.17a-4.com/skype-server-dataparser/) を使用して、Skype for Business Server から組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。 DataParser には、サード Skype for Business データ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された、Microsoft 365。 データSkype for Business Server DataParser コネクタは、Skype for Business Serverデータを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

ユーザー Skype for Business Serverにデータを格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 アプリケーション コネクタSkype for Business Serverを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-skype-for-business-server-data"></a>データのアーカイブSkype for Business Server概要

次の概要では、データ コネクタを使用してデータをアーカイブするプロセスSkype for Business Server説明Microsoft 365。

![17a-4 Skype for Business Serverデータのアーカイブ ワークフロー。](../media/SkypeServerDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して、DataParser のSkype for Business Server構成します。

2. 定期的に、データSkype for Business Server DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成する Skype for Business Server DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. **Skype for Business Server DataParser という名前の受信** トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、Skype for Business Serverアイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべてのSkype for Business Serverには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには、 [17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で Skype for Business Server DataParser コネクタを作成し、手順 3 で完了するユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この 17a-4 データ コネクタは、米国政府機関GCC環境Microsoft 365利用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-a-skype-for-business-server-dataparser-connector"></a>手順 1: DataParser コネクタSkype for Business Serverセットアップする

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、Skype for Business Server用の 17a-4 コネクタを作成することです。

1. [データ コネクタ<https://compliance.microsoft.com>] に移動し、[**DataParser** >  **Skype for Business Server] をクリックします**。

2. [**DataParser Skype for Business Server説明] ページで、[** コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、DataParser 接続ウィザードの手順Skype for Business Server完了します。

## <a name="step-2-configure-the-skype-for-business-server-dataparser-connector"></a>手順 2: DataParser コネクタSkype for Business Server構成する

17a-4 サポートを使用して、DataParser コネクタSkype for Business Server構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

DataParser Skype for Business Serverデータをインポートする前に、DataParser コネクタはユーザーを電子メール アドレスMicrosoft 365に自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-skype-for-business-server-dataparser-connector"></a>手順 4: DataParser コネクタSkype for Business Server監視する

DataParser Skype for Business Serverを作成した後、コネクタの状態を[データ] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション <https://compliance.microsoft.com> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した Skype for Business Server DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。

---
title: データをアーカイブするコネクタをSkype for Business ServerするMicrosoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 17a-4 Skype for Business Server DataParser コネクタをセットアップして使用して、Skype for Business Server データをインポートおよびアーカイブするMicrosoft 365。
ms.openlocfilehash: 1cbb0873a86af099665cf8bf6353ce351bafb3cd
ms.sourcegitcommit: 9469d16c6bbd29442a6787beaf7d84fb7699c5e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58400417"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-server-data"></a>データをアーカイブするコネクタをSkype for Business Serverする

17a-4 [LLC Skype Server DataParser](https://www.17a-4.com/skype-server-dataparser/)を使用して、Skype for Business Server から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には、サード Skype for Business データ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された、Microsoft 365。 DataParser Skype for Business Serverコネクタは、Skype for Business Serverデータを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

ユーザー Skype for Business Serverにデータが格納された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 アプリケーション コネクタSkype for Business Serverを使用して、データをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-skype-for-business-server-data"></a>データのアーカイブSkype for Business Server概要

次の概要では、データ コネクタを使用してデータをアーカイブするプロセスSkype for Business Server説明Microsoft 365。

![17a-4 Skype for Business Serverデータのアーカイブ ワークフロー](../media/SkypeServerDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して、DataParser のSkype for Business Server構成します。

2. 定期的に、データSkype for Business Server DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Skype for Business Serverで作成する Microsoft 365 コンプライアンス センター DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護されたAzure Storage場所にメッセージを転送します。

4. **Skype for Business Server DataParser という名前** の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、Skype for Business Serverアイテムがそのフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべてのSkype for Business Serverには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で Skype for Business Server DataParser コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-a-skype-for-business-server-dataparser-connector"></a>手順 1: DataParser コネクタSkype for Business Serverセットアップする

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、Skype for Business Server用の 17a-4 コネクタをSkype for Business Serverします。

1. <https://compliance.microsoft.com>[DataParser] に移動し、[**データ** コネクタ  >  **] Skype for Business Serverクリックします**。

2. **[DataParser Skype for Business Server説明] ページで、[** コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、DataParser 接続ウィザードの手順Skype for Business Server完了します。

## <a name="step-2-configure-the-skype-for-business-server-dataparser-connector"></a>手順 2: DataParser コネクタSkype for Business Server構成する

17a-4 サポートを使用して、DataParser コネクタSkype for Business Server構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

データSkype for Business Serverデータをインポートする前に、DataParser コネクタは自動的にユーザー Microsoft 365メール アドレスにマップMicrosoft 365。

## <a name="step-4-monitor-the-skype-for-business-server-dataparser-connector"></a>手順 4: DataParser コネクタSkype for Business Server監視する

DataParser コネクタSkype for Business Server作成した後、コネクタの状態を [データ] Microsoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した Skype for Business Server DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。

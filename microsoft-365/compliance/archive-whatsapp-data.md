---
title: Microsoft 365で WhatsApp データをアーカイブするコネクタを設定する
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
description: 管理者は、Microsoft 365で WhatsApp データをインポートおよびアーカイブする TeleMessage コネクタを設定できます。 これにより、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできるため、訴訟ホールド、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティのデータを管理できます。
ms.openlocfilehash: e473e9a83bd035209cbc2cb07aa3fb93386e47d9
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "65000446"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>WhatsApp データをアーカイブするコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルの TeleMessage コネクタを使用して、WhatsApp の呼び出し、チャット、添付ファイル、ファイル、および削除されたメッセージをインポートおよびアーカイブします。 コネクタを設定して構成すると、組織の TeleMessage アカウントに毎日 1 回接続され、TeleMessage WhatsApp 電話 Archiver または TeleMessage WhatsApp Cloud Archiver を使用して従業員のモバイル通信をMicrosoft 365のメールボックスにインポートします。

WhatsApp データがユーザー メールボックスに格納された後、訴訟ホールド、コンテンツ検索、Microsoft 365アイテム保持ポリシーなどの Microsoft Purview 機能を WhatsApp データに適用できます。 たとえば、コンテンツ検索を使用して WhatsApp メッセージを検索したり、WhatsApp メッセージを含むメールボックスを電子情報開示 (プレミアム) ケースのカストディアンに関連付けることができます。 WhatsApp コネクタを使用してMicrosoft 365のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-whatsapp-data"></a>WhatsApp データのアーカイブの概要

次の概要では、コネクタを使用して WhatsApp データをMicrosoft 365にアーカイブするプロセスについて説明します。

![WhatsApp アーカイブ ワークフロー。](../media/WhatsAppConnectorWorkflow.png)

1. 組織は TeleMessage と連携して WhatsApp Archiver コネクタを設定します。 詳細については、「 [WhatsApp Archiver」を](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)参照してください。

2. リアルタイムで、組織の WhatsApp データが TeleMessage サイトにコピーされます。

3. コンプライアンス ポータルで作成した WhatsApp コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の WhatsApp データを Microsoft クラウド内の安全なAzure Storageの場所に転送します。 また、コネクタはコンテンツ WhatsApp データを電子メール メッセージ形式に変換します。

4. コネクタは、WhatsApp データを特定のユーザーのメールボックスにインポートします。 **WhatsApp Archiver** という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メール アドレス* プロパティの値を使用してこのマッピングを行います。 すべての WhatsApp メッセージには、このプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メール アドレスが設定されます。

   *ユーザーの電子メール アドレス* プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを実装することもできます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号と対応するMicrosoft 365電子メール アドレスが含まれています。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべての WhatsApp アイテムについて、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効なMicrosoft 365ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 カスタム マッピング ファイルまたは WhatsApp アイテムのメール アドレス プロパティで有効なMicrosoft 365 ユーザーがコネクタで見つからない場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

WhatsApp 通信データをアーカイブするために必要な実装手順の一部はMicrosoft 365外部にあり、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から WhatsApp Archiver サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成するときは、このアカウントにサインインする必要があります。

- TeleMessage アカウントで WhatsApp アーカイブを必要とするすべてのユーザーを登録します。 ユーザーを登録するときは、Microsoft 365 アカウントに使用するのと同じメール アドレスを必ず使用してください。

- TeleMessage [WhatsApp 電話 Archiver アプリ](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/)を従業員の携帯電話にインストールし、アクティブ化します。 または、従業員の携帯電話に通常の WhatsApp または WhatsApp Business アプリをインストールし、TeleMessage Web サイトで QR コードをスキャンして WhatsApp Cloud Archiver サービスをアクティブ化することもできます。 詳細については、「 [WhatsApp Cloud Archiver」を](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)参照してください。

- Verizon ネットワーク コネクタを作成するユーザーには、データ コネクタ管理者ロールが割り当てられている必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- この TeleMessage データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境で使用できます。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purview およびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="create-a-whatsapp-archiver-connector"></a>WhatsApp Archiver コネクタを作成する

前のセクションで説明した前提条件を完了したら、コンプライアンス ポータルで WhatsApp コネクタを作成できます。 コネクタは、指定した情報を使用して TeleMessage サイトに接続し、WhatsApp データをMicrosoft 365の対応するユーザー メールボックス ボックスに転送します。

1. **Data connectorsWhatsApp** >  **Archiver** に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動してクリックします。

2. **WhatsApp Archiver** 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [手順 3] で、次のボックスに必要な情報を入力し、[ **次へ**] をクリックします。

   - **名：** TeleMessage ユーザー名。

   - **パスワード：** TeleMessage のパスワード。

5. コネクタが作成されたら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ **ユーザー マッピング** ] ページで、自動ユーザー マッピングを有効にして、[ **次へ**] をクリックします。 カスタム マッピングで CSV ファイルをアップロードする必要がある場合は、[ **次へ**] をクリックします。

7. 設定を確認し、[ **完了]** をクリックしてコネクタを作成します。

8. **[データ コネクタ**] ページの [コネクタ] タブに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。

---
title: Microsoft 365で Verizon Network データをアーカイブするコネクタを設定する
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
description: 管理者は TeleMessage コネクタを設定して、Microsoft 365の Verizon Network から SMS および MMS データをインポートおよびアーカイブできます。 これにより、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできるため、訴訟ホールド、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティのデータを管理できます。
ms.openlocfilehash: 5df1adad87c9995caeed4e090a7db0e7fbdf7566
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64936975"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>Verizon Network データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの TeleMessage コネクタを使用して、Verizon Network からショート メッセージング サービス (SMS) とマルチメディア メッセージング サービス (MMS) のデータをインポートおよびアーカイブします。 コネクタを設定して構成すると、組織の Verizon Network に毎日 1 回接続され、SMS と MMS のデータがMicrosoft 365のメールボックスにインポートされます。

Verizon Network コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、コンテンツ検索、Microsoft 365アイテム保持ポリシーなどの Microsoft Purview 機能を Verizon データに適用できます。 たとえば、コンテンツ検索を使用して Verizon SMS および MMS メッセージを検索したり、Verizon Network データを含むメールボックスを Microsoft Purview 電子情報開示 (プレミアム) ケースのカストディアンに関連付けることができます。 Verizon ネットワーク コネクタを使用してMicrosoft 365にデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-verizon-network-data"></a>Verizon Network データのアーカイブの概要

次の概要では、コネクタを使用して Verizon Network データをMicrosoft 365にアーカイブするプロセスについて説明します。

![Verizon Network アーカイブ ワークフロー。](../media/VerizonNetworkConnectorWorkflow.png)

1. 組織は TeleMessage と Verizon と連携して Verizon ネットワーク コネクタを設定します。 詳細については、「 [Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/)」を参照してください。

2. 24 時間に 1 回、組織の Verizon Network からの SMS メッセージと MMS メッセージが TeleMessage サイトにコピーされます。

3. コンプライアンス ポータルで作成した Verizon Network コネクタは、TeleMessage サイトに毎日接続され、前の 24 時間の SMS および MMS メッセージを Microsoft クラウド内の安全なAzure Storageの場所に転送します。 また、コネクタは SMS メッセージと MMS メッセージのコンテンツを電子メール メッセージ形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 **Verizon SMS/MMS Network Archiver** という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メール アドレス* プロパティの値を使用してこのマッピングを行います。 すべての SMS および MMS メッセージには、このプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メール アドレスが入力されます。

   *ユーザーの電子メール アドレス* プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを実装することもできます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号と対応するMicrosoft 365電子メール アドレスが含まれています。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべての Verizon 項目について、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効なMicrosoft 365ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたは Verizon アイテムのメール アドレス プロパティで有効なMicrosoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

Verizon Network データをアーカイブするために必要な実装手順の一部はMicrosoft 365外部にあり、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から Verizon Network Archiver サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成するときは、このアカウントにサインインする必要があります。

- TeleMessage オンボード フォームに入力し、Verizon からメッセージ アーカイブ サービスを注文できるように、Verizon Network アカウントと課金連絡先の詳細を取得します。

- TeleMessage アカウントで Verizon SMS と MMS のアーカイブを必要とするすべてのユーザーを登録します。 ユーザーを登録するときは、Microsoft 365 アカウントに使用するのと同じメール アドレスを必ず使用してください。

- 従業員は、Verizon モバイル ネットワーク上に会社所有の携帯電話と会社の責任を負う携帯電話を持っている必要があります。 Microsoft 365のメッセージのアーカイブは、従業員所有のデバイスまたは Bring Your Own Devices (BYOD) デバイスでは使用できません。

- Verizon ネットワーク コネクタを作成するユーザーには、データ コネクタ管理者ロールが割り当てられている必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- この TeleMessage データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境で使用できます。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purview およびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="create-a-verizon-network-connector"></a>Verizon ネットワーク コネクタを作成する

前のセクションで説明した前提条件を完了したら、コンプライアンス ポータルで Verizon Network コネクタを作成できます。 コネクタは、指定した情報を使用して TeleMessage サイトに接続し、SMS および MMS メッセージをMicrosoft 365の対応するユーザー メールボックス ボックスに転送します。

1. **Data** **connectorsVerizon** >  Network に [https://compliance.microsoft.com](https://compliance.microsoft.com)移動してクリックします。

2. **Verizon Network** 製品の説明ページで、[**コネクタの追加**] をクリックします。

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
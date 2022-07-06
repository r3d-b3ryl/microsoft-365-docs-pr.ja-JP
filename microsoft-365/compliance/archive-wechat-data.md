---
title: Microsoft 365 で WeChat データをアーカイブするコネクタを設定する
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
description: Microsoft Purview コンプライアンス ポータルでコネクタを設定して使用して、Microsoft 365 で WeChat データをインポートしてアーカイブします。
ms.openlocfilehash: 1cc5ce3f15f8e40f5515dbac046fce8370a4252c
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630599"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>WeChat データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの TeleMessage コネクタを使用して、WeChat と WeCom の通話、チャット、添付ファイル、ファイル、およびリコールされたメッセージをインポートおよびアーカイブします。 コネクタを設定して構成すると、組織の TeleMessage アカウントに接続され、TeleMessage WeChat Archiver を使用して従業員のモバイル通信が Microsoft 365 のメールボックスにインポートされます。

WeChat Archiver コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、In-Placeアーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft Purview 機能を WeChat 通信データに適用できます。 たとえば、コンテンツ検索を使用して WeChat 通信を検索したり、WeChat Archiver コネクタ データを含むメールボックスを電子情報開示 (Premium) ケースのカストディアンに関連付けることができます。 WeChat Archiver コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が企業ガバナンス規制や規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-wechat-communication-data"></a>WeChat 通信データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で WeChat 通信データをアーカイブするプロセスについて説明します。

![WeChat Archiver データのアーカイブ ワークフロー。](../media/WeChatConnectorWorkflow.png)

1. 組織は TeleMessage と連携して、WeChat Archiver コネクタを設定します。

2. リアルタイムで、組織の WeChat データが TeleMessage サイトにコピーされます。

3. コンプライアンス ポータルで作成した WeChat Archiver コネクタは、毎日 TeleMessage サイトに接続し、前の 24 時間のメール メッセージを Microsoft Cloud のセキュリティで保護された Azure Storage 領域に転送します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 WeChat Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メール アドレス* プロパティの値を使用してマッピングを行います。 すべての電子メール メッセージには、このプロパティが含まれています。このプロパティには、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 *ユーザーの電子メール アドレス* プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義することもできます。 このマッピング ファイルには、ユーザーの携帯電話番号と、各ユーザーの対応する Microsoft 365 メールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にし、カスタム マッピングを指定する場合は、すべての電子メール アイテムについて、コネクタが最初にカスタム マッピング ファイルを確認します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 カスタム マッピング ファイルまたは電子メール アイテムのユーザーの *電子メール アドレス* プロパティで有効な Microsoft 365 ユーザーがコネクタで見つからない場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- TeleMessage を使用して WeChat アーカイブ コネクタを設定します。 詳細については、「 [Microsoft 365 用 TeleMessage WeChat Archiver のアクティブ化」を](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)参照してください。

- Microsoft 365 用の TeleMessage コネクタを設定し、有効な会社管理アカウントを取得します。 詳細については、「 [Order Microsoft 365 Mobile アーカイブ](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)」を参照してください。

- TeleMessage アカウントで WeChat アーカイブを必要とするすべてのユーザーを、ユーザーの Microsoft 365 アカウントに使用するのと同じ電子メール アドレスで登録します。

- 組織内のユーザーの携帯電話に Tencent WeCom アプリをインストールし、アクティブ化する必要があります。 WeCom アプリを使用すると、ユーザーは他の WeChat ユーザーや WeCom ユーザーと通信してチャットできます。

- コンプライアンス ポータルで WeChat Archiver コネクタを作成するユーザーには、Data Connector 管理 ロールが割り当てられている必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この TeleMessage データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="create-a-wechat-archiver-connector"></a>WeChat Archiver コネクタを作成する

このセクションの手順に従って、コンプライアンス ポータルで WeChat Archiver コネクタを作成します。 コネクタは、指定した情報を使用して TeleMessage サイトに接続し、WeChat 通信データを Microsoft 365 の対応するユーザー メールボックスに転送します。

1. **データ コネクタ** > **WeChat Archiver** に<https://compliance.microsoft.com>移動してクリックします。

2. **WeChat Archiver** 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [手順 3] で、次のボックスに必要な情報を入力し、[ **次へ**] をクリックします。

    - **ユーザー名**: TeleMessage ユーザー名。

    - **パスワード**: TeleMessage のパスワード。

5. コネクタが作成されたら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ **ユーザー マッピング** ] ページで、自動ユーザー マッピングを有効にします。 カスタム ユーザー マッピング CSV ファイルをアップロードすることもできます。

7. [ **次へ**] をクリックし、設定を確認し、[ **完了]** をクリックしてコネクタを作成します。

8. **[データ コネクタ**] ページ **の [コネクタ**] タブに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。

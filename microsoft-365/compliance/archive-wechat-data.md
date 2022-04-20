---
title: Microsoft 365で WeChat データをアーカイブするコネクタを設定する
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
description: Microsoft Purview コンプライアンス ポータルでコネクタを設定して使用して、Microsoft 365で WeChat データをインポートしてアーカイブします。
ms.openlocfilehash: e504c9fd3440e0ccc232e91838ef52577b1552be
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64942823"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>WeChat データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの TeleMessage コネクタを使用して、WeChat と WeCom の通話、チャット、添付ファイル、ファイル、およびリコールされたメッセージをインポートおよびアーカイブします。 コネクタを設定して構成すると、組織の TeleMessage アカウントに接続され、TeleMessage WeChat Archiver を使用して従業員のモバイル通信がMicrosoft 365のメールボックスにインポートされます。

WeChat Archiver コネクタ データがユーザー メールボックスに格納されたら、訴訟ホールド、電子情報開示、In-Placeアーカイブ、監査、通信コンプライアンス、Microsoft 365アイテム保持ポリシーなどの Microsoft Purview 機能を WeChat 通信データに適用できます。 たとえば、コンテンツ検索を使用して WeChat 通信を検索したり、WeChat Archiver コネクタ データを含むメールボックスを電子情報開示 (プレミアム) ケースのカストディアンに関連付けることができます。 WeChat Archiver コネクタを使用してMicrosoft 365にデータをインポートおよびアーカイブすると、組織が企業ガバナンスの規制や規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-wechat-communication-data"></a>WeChat 通信データのアーカイブの概要

次の概要では、コネクタを使用して WeChat 通信データをMicrosoft 365にアーカイブするプロセスについて説明します。

![WeChat Archiver データのアーカイブ ワークフロー。](../media/WeChatConnectorWorkflow.png)

1. 組織は TeleMessage と連携して、WeChat Archiver コネクタを設定します。

2. リアルタイムで、組織の WeChat データが TeleMessage サイトにコピーされます。

3. コンプライアンス ポータルで作成した WeChat Archiver コネクタは、毎日 TeleMessage サイトに接続され、前の 24 時間のメール メッセージを Microsoft Cloud のセキュリティで保護されたAzure Storage領域に転送します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 WeChat Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メール アドレス* プロパティの値を使用してマッピングを行います。 すべての電子メール メッセージには、このプロパティが含まれています。このプロパティには、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 *ユーザーの電子メール アドレス* プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義することもできます。 このマッピング ファイルには、ユーザーの携帯電話番号と、各ユーザーの対応するMicrosoft 365メールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にし、カスタム マッピングを指定する場合は、すべての電子メール アイテムについて、コネクタが最初にカスタム マッピング ファイルを確認します。 ユーザーの携帯電話番号に対応する有効なMicrosoft 365 ユーザーが見つからない場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 コネクタで、カスタム マッピング ファイルまたは電子メール アイテムのユーザーの *電子メール アドレス* プロパティで有効なMicrosoft 365 ユーザーが見つからない場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- TeleMessage を使用して WeChat アーカイブ コネクタを設定します。 詳細については、「[Microsoft 365の TeleMessage WeChat Archiver のアクティブ化」を](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)参照してください。

- Microsoft 365の TeleMessage コネクタを設定し、有効な会社管理アカウントを取得します。 詳細については、「[Order Microsoft 365 Mobile アーカイブ](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)」を参照してください。

- TeleMessage アカウントで WeChat アーカイブを必要とするすべてのユーザーを、ユーザーのMicrosoft 365 アカウントに使用するのと同じ電子メール アドレスで登録します。

- 組織内のユーザーの携帯電話に Tencent WeCom アプリをインストールし、アクティブ化する必要があります。 WeCom アプリを使用すると、ユーザーは他の WeChat ユーザーや WeCom ユーザーと通信してチャットできます。

- コンプライアンス ポータルで WeChat Archiver コネクタを作成するユーザーには、データ コネクタ管理者ロールが割り当てられている必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- この TeleMessage データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境で使用できます。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purview およびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="create-a-wechat-archiver-connector"></a>WeChat Archiver コネクタを作成する

このセクションの手順に従って、コンプライアンス ポータルで WeChat Archiver コネクタを作成します。 コネクタは、指定した情報を使用して TeleMessage サイトに接続し、WeChat 通信データをMicrosoft 365の対応するユーザー メールボックスに転送します。

1. **Data connectorsWeChat** >  **Archiver** に<https://compliance.microsoft.com>移動してクリックします。

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

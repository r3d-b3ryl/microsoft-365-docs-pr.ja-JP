---
title: WeChat データをアーカイブするコネクタをセットアップMicrosoft 365
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
description: WeChat データをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターでコネクタを設定して使用Microsoft 365。
ms.openlocfilehash: f2adb42dfd8145658e8861c752cfb9c11e306f52
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328219"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>WeChat データをアーカイブするコネクタをセットアップする

WeChat 通話、WeCom 通話、チャット、添付Microsoft 365 コンプライアンス センター、および呼び出し後のメッセージをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センター の TeleMessage コネクタを使用します。 コネクタをセットアップして構成すると、そのコネクタは組織の TeleMessage アカウントに接続し、TeleMessage WeChat Archiver を使用して従業員のモバイル通信を Microsoft 365 のメールボックスにインポートします。

WeChat Archiver コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を WeChat 通信データに適用できます。 たとえば、コンテンツ検索を使用して WeChat 通信を検索したり、WeChat Archiver コネクタ データを含むメールボックスを、特定のケースの保管担当者Advanced eDiscoveryできます。 WeChat Archiver コネクタを使用してデータをインポートおよびアーカイブすると、Microsoft 365ガバナンス規制と規制ポリシーに準拠し、組織を支援できます。

## <a name="overview-of-archiving-wechat-communication-data"></a>WeChat 通信データのアーカイブの概要

次の概要では、コネクタを使用して WeChat 通信データをアーカイブするプロセスについて説明Microsoft 365。

![WeChat Archiver データのアーカイブ ワークフロー。](../media/WeChatConnectorWorkflow.png)

1. 組織は TeleMessage を使用して WeChat Archiver コネクタをセットアップします。

2. リアルタイムで、組織の WeChat データが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センター で作成した WeChat Archiver コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の電子メール メッセージを Microsoft Cloud の安全な Azure Storage 領域に転送します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 WeChat Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用 *してマッピングを行* います。 すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、ユーザーのモバイル番号と、各ユーザー Microsoft 365対応するメールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にしてカスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 コネクタがカスタム マッピング ファイルまたは電子メール アイテムのユーザーの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- TeleMessage を使用して WeChat アーカイブ コネクタをセットアップします。 詳細については、「[TeleMessage WeChat Archiver for the TeleMessage WeChat Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)。

- ユーザーに対して TeleMessage コネクタをMicrosoft 365有効な会社の管理アカウントを取得します。 詳細については、「Order [Microsoft 365 モバイル アーカイブ」を参照してください](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)。

- TeleMessage アカウントで WeChat アーカイブが必要なすべてのユーザーを、ユーザーのアカウントに使用されるのと同じ電子メール アドレスMicrosoft 365します。

- 組織のユーザーの携帯電話に Tencent WeCom アプリをインストールし、アクティブ化する必要があります。 WeCom アプリを使用すると、ユーザーは他の WeChat ユーザーや WeCom ユーザーと通信してチャットできます。

- データ コネクタに WeChat Archiver コネクタを作成するMicrosoft 365 コンプライアンス センター、データ コネクタ管理者の役割を割り当てる必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この TeleMessage データ コネクタは、米国政府機関GCC環境Microsoft 365使用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="create-a-wechat-archiver-connector"></a>WeChat Archiver コネクタの作成

このセクションの手順に従って、このセクションで WeChat Archiver コネクタを作成Microsoft 365 コンプライアンス センター。 コネクタは、指定した情報を使用して、TeleMessage サイトに接続し、WeChat 通信データをネットワーク内の対応するユーザー メールボックスに転送Microsoft 365。

1. [データ コネクタ<https://compliance.microsoft.com>**WeChat Archiver] に移動し、[データ コネクタ] をクリックします** > 。

2. **[WeChat Archiver 製品の説明] ページ** で、[コネクタの追加] **をクリックします。**

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. [ **TeleMessage へのログイン]** ページの [手順 3] で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

    - **ユーザー** 名: TeleMessage ユーザー名。

    - **パスワード**: TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にする。 カスタム ユーザー マッピング CSV ファイルをアップロードできます。

7. [ **次へ**] をクリックし、設定を確認し、[ **完了] をクリックして** コネクタを作成します。

8. [データ コネクタ **] ページの** [ **コネクタ** ] タブに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。

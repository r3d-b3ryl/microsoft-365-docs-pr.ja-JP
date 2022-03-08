---
title: テレグラム通信データをアーカイブするコネクタを設定Microsoft 365
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
description: 管理者は、TeleMessage コネクタをセットアップして、テレグラム通信データをインポートおよびアーカイブMicrosoft 365。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティデータを管理できます。
ms.openlocfilehash: 2fbe0a97572d13b6d2ba6e26ac02fd5ee8817b8a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312293"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data"></a>テレグラム通信データをアーカイブするコネクタをセットアップする

メッセージ の TeleMessage コネクタを使用Microsoft 365 コンプライアンス センター、Telegram チャット、添付ファイル、削除されたメッセージと通話をインポートおよびアーカイブします。 コネクタを設定して構成すると、そのコネクタは組織の TeleMessage アカウントに接続し、テレグラム アーカイブを使用する従業員のモバイル通信を Microsoft 365 のメールボックスにインポートします。

Telegram Archiver コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、コンテンツ検索、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をテレグラム通信データに適用できます。 たとえば、コンテンツ検索を使用してテレグラム通信を検索したり、Telegram Archiver コネクタ データを含むメールボックスを保管担当者に関連付Advanced eDiscoveryできます。 Telegram Archiver コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織がコーポレート ガバナンス規制や規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-telegram-communications-data"></a>テレグラム通信データのアーカイブの概要

次の概要では、コネクタを使用してテレグラム通信データをアーカイブするプロセスを、Microsoft 365。

![テレグラム通信アーカイブ ワークフロー。](../media/TelegramConnectorWorkflow.png)

1. 組織は TeleMessage と一緒にテレグラム アーカイブ コネクタをセットアップします。 詳細については、「[TeleMessage Telegram Archiver for the TeleMessage Archiver for Microsoft 365」 を参照してください](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/)。

2. リアルタイムで、組織の Telegram データが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センター で作成したテレグラム アーカイブ コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の電子メール メッセージを Microsoft Cloud の安全な Azure Storage 領域に転送します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 Telegram Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用して *、このマッピングを実行* します。 すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。

> *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、ユーザーのモバイル番号と、各ユーザー Microsoft 365対応するメールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にしてカスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 コネクタがカスタム マッピング ファイルまたは電子メール アイテムのユーザーの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- [Telegram アーカイブ サービスを TeleMessage から注文し](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。

- TeleMessage アカウントで Telegram アーカイブが必要なすべてのユーザーを登録します。 ユーザーを登録する場合は、ユーザーのアカウントに使用する電子メール アドレスと同じMicrosoft 365してください。

- 従業員の携帯電話に Telegram Archiver アプリをインストールし、アクティブ化します。 Telegram Archiver アプリを使用すると、他の Telegram ユーザーと通信してチャットできます。

- 手順 3 で Telegram Archiver コネクタを作成するユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この TeleMessage データ コネクタは、米国政府機関GCC環境Microsoft 365使用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="create-a-telegram-archiver-connector"></a>テレグラム アーカイブ コネクタの作成

前のセクションで説明した前提条件を完了したら、このセクションで Telegram Archiver コネクタを作成Microsoft 365 コンプライアンス センター。 コネクタは、指定した情報を使用して、TeleMessage サイトに接続し、テレグラム通信データを、ネットワーク内の対応するユーザー メールボックス ボックスに転送Microsoft 365。

1. [**Telegram**<https://compliance.microsoft.com> Archiver] **に** 移動し、[データ コネクタ] >クリックします。

2. [ **Telegram Archiver 製品の説明] ページ** で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. [ **TeleMessage へのログイン]** ページの [手順 3] で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

    - **ユーザー名:** TeleMessage ユーザー名。

    - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にする。 カスタム マッピングを有効にするには、ユーザー マッピング情報を含む CSV ファイルをアップロードし、[次へ] をクリック **します**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. [データ コネクタ] ページの [ **コネクタ] タブに移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。

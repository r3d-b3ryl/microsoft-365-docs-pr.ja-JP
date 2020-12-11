---
title: Android モバイル データをアーカイブするコネクタを設定する
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
description: 管理者は、Android 携帯電話から SMS、MMS、および音声通話をインポートおよびアーカイブする TeleMessage コネクタを設定できます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 5837d5247ca7ac82389d2781110883058ca98bb7
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620532"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Android モバイル データをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの TeleMessage コネクタを使用して、SMS、MMS、音声通話、通話ログを Android 携帯電話からインポートおよびアーカイブします。 コネクタをセットアップして構成した後、組織の TeleMessage アカウントに毎日 1 回接続し、TeleMessage Android Archiver を使用して従業員のモバイル通信を Microsoft 365 のメールボックスにインポートします。

Android 携帯電話のデータがユーザー メールボックスに保存された後、訴訟ホールド、コンテンツ検索、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を Android アーカイブ データに適用できます。 たとえば、コンテンツ検索を使用して Android Archiver モバイル通信を検索したり、Android アーカイブ コネクタ データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 Android アーカイブ コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-android-mobile-data"></a>Android モバイル データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Android モバイル データをアーカイブするプロセスについて説明します。

![Android アーカイブ コネクタのワークフロー](../media/AndroidArchiverConnectorWorkflow.png)

1. 組織は TeleMessage と一緒に Android アーカイブ コネクタをセットアップします。 詳細については [、「Android Archiver」を参照してください](https://www.telemessage.com/office365-activation-for-android-archiver/)。

2. 24 時間ごとに、組織の Android 携帯電話からの SMS、MMS、音声通話、通話ログが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センターで作成する Android アーカイブ コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の Android データを Microsoft Cloud のセキュリティで保護された Azure Storage の場所に転送します。 コネクタは、Android データを電子メール メッセージ形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 Android Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、ユーザーの電子メール アドレス プロパティの値 *を使用してマッピングを行* います。 すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 ユーザーの電子メール アドレス プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、ユーザーのモバイル番号と、各ユーザーの対応する Microsoft 365 メールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にしてカスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 コネクタがメール アイテムのカスタム マッピング ファイルまたはユーザーの電子メール アドレス プロパティに有効なMicrosoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

Android 通信データをアーカイブするために必要な実装手順の一部は Microsoft 365 の外部にあるので、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から Android Archiver サービスを注文](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)し、組織の有効な管理アカウントを取得します。 コネクタを作成するときに、このアカウントにサインインする必要があります。

- TeleMessage アカウントに Android アーカイブ サービスを必要とするユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントと同じメール アドレスを使用してください。

- 従業員の携帯電話に TeleMessage Android Archiver アプリをインストールしてアクティブ化します。

- Android アーカイブ コネクタを作成するユーザーには、Exchange Online の Mailbox Import Export 役割が割り当てられている必要があります。 これは、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="create-an-android-archiver-connector"></a>Android アーカイブ コネクタを作成する

最後の手順では、Microsoft 365 コンプライアンス センターで Android アーカイブ コネクタを作成します。 このコネクタは、指定した情報を使用して TeleMessage サイトに接続し、Microsoft 365 の対応するユーザー メールボックス ボックスに Android 通信を転送します。

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors**  >  **Android Archiver**.

2. Android アーカイブ **製品の説明ページ** で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. **[TeleMessage へのログイン**] ページの手順 3 で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタが作成された後、ポップアップ ウィンドウを閉じて 、[次へ] をクリック **します**。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にし、[次へ] を **クリックします**。 カスタム マッピングで CSV ファイルをアップロードする必要がある場合は、[次へ] をクリック **します**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. [データ コネクタ] ページの [コネクタ] タブに **移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。

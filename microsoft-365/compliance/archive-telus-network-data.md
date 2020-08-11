---
title: Microsoft 365 の TELUS ネットワークデータをアーカイブするためのコネクタの設定
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、TeleMessage コネクタをセットアップして、Microsoft 365 の TELUS ネットワークから SMS データをインポートおよびアーカイブすることができます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: a2d7796693d1c53c1f73d6fc227b5a40ffa98880
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602226"
---
# <a name="set-up-a-connector-to-archive-telus-network-data-preview"></a>TELUS ネットワークデータをアーカイブするためのコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンスセンターの TeleMessage コネクタを使用して、組織の TELUS ネットワークからの短いメッセージングサービス (SMS) データのインポートとアーカイブを行います。 コネクタをセットアップして構成した後は、組織の TELUS ネットワークに毎日接続し、SMS データを Microsoft 365 のメールボックスにインポートします。

SMS メッセージをユーザーのメールボックスに格納した後、訴訟ホールド、コンテンツ検索、Microsoft 365 のアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を TELUS データに適用することができます。 たとえば、コンテンツ検索を使用して TELUS SMS メッセージを検索したり、TELUS データを含むメールボックスを高度な電子情報開示ケースの保管担当者に関連付けることができます。 TELUS ネットワークコネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることで、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-telus-network-data"></a>TELUS ネットワークデータのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の TELUS ネットワークデータをアーカイブするプロセスについて説明します。

![TELUS ネットワークアーカイブワークフロー](../media/TelusNetworkConnectorWorkflow.png)

1. 組織は TeleMessage と TELUS を使用して、TELUS ネットワークコネクタを設定します。 詳細については、「 [TELUS Network Archiver](https://www.telemessage.com/office365-activation-for-telus-network-archiver/)」を参照してください。

2. 24時間ごとに、組織の TELUS ネットワークからの SMS メッセージは TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成した TELUS ネットワークコネクタが、毎日 TeleMessage サイトに接続し、SMS メッセージを前の24時間から Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。 また、このコネクタは、SMS メッセージの内容を電子メールメッセージの形式に変換します。

4. コネクタは、特定のユーザーのメールボックスにモバイル通信アイテムをインポートします。 **TELUS SMS Network Archiver**という名前の新しいフォルダーが、特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、*ユーザーの電子メールアドレス*プロパティの値を使用してマッピングを行います。 すべての SMS メッセージには、このプロパティが含まれており、SMS メッセージのすべての参加者の電子メールアドレスが設定されます。

   *ユーザーの電子メールアドレス*プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを実装することもできます。 このマッピングファイルには、組織内のユーザーの携帯電話番号と、対応する Microsoft 365 メールアドレスが含まれています。 自動ユーザーマッピングとカスタムマッピングの両方を有効にした場合、TELUS アイテムごとに、コネクタは最初にカスタムマッピングファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムの [電子メールアドレス] プロパティの値を使用します。 コネクタがカスタムマッピングファイルまたは TELUS item の電子メールアドレスプロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

TELUS ネットワークデータをアーカイブするために必要な実装手順の多くは、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に、完了する必要があります。

- [TeleMessage から TELUS ネットワークアーカイバサービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文して、組織の有効な管理アカウントを取得します。 コンプライアンスセンターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- TELUS ネットワークアカウントと請求連絡先の詳細を取得して、TeleMessage のオンボードフォームに記入し、TELUS からメッセージアーカイブサービスを注文できるようにします。

- TELUS の SMS ネットワークアーカイブを必要とするすべてのユーザーを TeleMessage アカウントに登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用しているのと同じ電子メールアドレスを使用してください。

- 従業員は、社内所有の携帯電話に、theTELUS のモバイルネットワーク上の携帯電話を保有している必要があります。 Microsoft 365 のアーカイブメッセージは、従業員が所有したり、独自のデバイス (BYOD) デバイスを使用したりすることはできません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この同意を得るには、コネクタを作成する必要があります。 この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 TELUS ネットワークコネクタを正常に作成するには、この手順を完了する必要があります。

- TELUS ネットワークコネクタを作成したユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [**データコネクタ**] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。

## <a name="create-a-telus-network-connector"></a>TELUS ネットワークコネクタを作成する

前のセクションで説明した前提条件を完了したら、Microsoft 365 コンプライアンスセンターで TELUS ネットワークコネクタを作成できます。 コネクタは、提供された情報を使用して、TeleMessage サイトに接続し、SMS メッセージを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データコネクタ**  >  **TELUS ネットワーク**] をクリックします。

2. **TELUS ネットワーク**製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [**サービス利用規約**] ページで、[**同意**する] をクリックします。

4. [ **TeleMessage へのログイン**] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[**次へ**] をクリックします。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage のパスワードを入力します。

5. コネクタが作成されたら、ポップアップウィンドウを閉じて次のページに進むことができます。

6. [**ユーザーマッピング**] ページで、[ユーザーマッピングの自動設定] を有効にして、[**次へ**] をクリックします。 カスタムマッピングが必要な場合は、CSV ファイルをアップロードし、[**次へ**] をクリックします。

7. 管理者の同意を得てから、[**次へ**] をクリックします。

   管理者の同意を得るには、Office 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

8. 設定内容を確認し、[**完了**] をクリックしてコネクタを作成します。

9. [**データコネクタ**] ページの [コネクタ] タブに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- コネクタは、10 MB を超えるアイテムをインポートしません。

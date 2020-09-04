---
title: Microsoft 365 で Verizon ネットワークデータをアーカイブするためのコネクタの設定
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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Microsoft 365 の Verizon ネットワークから SMS および MMS データをインポートしてアーカイブするための TeleMessage コネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: c088adbd0e0a5d4a46b3f7ddb3d64d3f8c32c8dc
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361832"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data-preview"></a>コネクタを設定して Verizon ネットワークデータをアーカイブする (プレビュー)

Microsoft 365 コンプライアンスセンターの TeleMessage コネクタを使用して、Verizon ネットワークからの短いメッセージングサービス (SMS) およびマルチメディアメッセージングサービス (MMS) データのインポートとアーカイブを行います。 コネクタをセットアップして構成した後は、組織の Verizon ネットワークに毎日接続し、SMS および MMS データを Microsoft 365 のメールボックスにインポートします。

Verizon ネットワークコネクタのデータがユーザーのメールボックスに格納された後、Microsoft 365 のコンプライアンス機能 (訴訟ホールド、コンテンツ検索、Microsoft 365 アイテム保持ポリシーなど) を Verizon データに適用することができます。 たとえば、コンテンツ検索を使用して Verizon SMS および MMS メッセージを検索したり、Verizon ネットワークデータを含むメールボックスを高度な電子情報開示ケースの保管担当者に関連付けることができます。 Microsoft 365 で、Verizon ネットワークコネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-verizon-network-data"></a>Verizon ネットワークデータのアーカイブの概要

次の概要では、コネクタを使用して、Microsoft 365 で Verizon ネットワークデータをアーカイブするプロセスについて説明します。

![Verizon ネットワークアーカイブワークフロー](../media/VerizonNetworkConnectorWorkflow.png)

1. 組織は、TeleMessage と Verizon を使用して、Verizon ネットワークコネクタを設定します。 詳細については、「 [Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/)」を参照してください。

2. 24時間ごとに、組織の Verizon ネットワークからの SMS および MMS メッセージは TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成した Verizon ネットワークコネクタは、TeleMessage サイトに毎日接続し、SMS および MMS メッセージを過去24時間から Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。 また、このコネクタは、SMS メッセージと MMS メッセージの内容を電子メールメッセージ形式に変換します。

4. コネクタは、特定のユーザーのメールボックスにモバイル通信アイテムをインポートします。 「 **VERIZON SMS/MMS Network Archiver** 」という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メールアドレス* プロパティの値を使用して、このマッピングを行います。 すべての SMS および MMS メッセージには、このプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メールアドレスが設定されます。

   *ユーザーの電子メールアドレス*プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを実装することもできます。 このマッピングファイルには、組織内のユーザーの携帯電話番号と、対応する Microsoft 365 メールアドレスが含まれています。 自動ユーザーマッピングとカスタムマッピングの両方を有効にした場合、すべての Verizon アイテムに対して、コネクタは最初にカスタムマッピングファイルを検索します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムの [電子メールアドレス] プロパティの値を使用します。 コネクタが、カスタムマッピングファイルまたは Verizon アイテムの電子メールアドレスプロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

Verizon ネットワークデータをアーカイブするために必要ないくつかの実装手順は、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から Verizon Network Archiver service](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文して、組織の有効な管理アカウントを取得します。 コンプライアンスセンターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- Verizon ネットワークアカウントと請求連絡先の詳細を取得して、TeleMessage のオンボードフォームに記入し、Verizon からメッセージアーカイブサービスを注文することができるようにします。

- TeleMessage アカウントに、Verizon SMS および MMS アーカイブを必要とするすべてのユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用しているのと同じ電子メールアドレスを使用してください。

- 従業員は、Verizon モバイルネットワーク上で企業所有の携帯電話と会社の責任を持つ携帯電話を所有している必要があります。 Microsoft 365 のアーカイブメッセージは、従業員が所有したり、独自のデバイス (BYOD) デバイスを使用したりすることはできません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この同意を得るには、コネクタを作成する必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 Verizon ネットワークコネクタを正常に作成するには、この手順を完了する必要があります。

- Verizon ネットワークコネクタを作成したユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="create-a-verizon-network-connector"></a>Verizon ネットワークコネクタを作成する

前のセクションで説明した前提条件を完了した後、Microsoft 365 コンプライアンスセンターで、Verizon ネットワークコネクタを作成できます。 コネクタは、提供された情報を使用して、TeleMessage サイトに接続し、SMS および MMS メッセージを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) し、[**データコネクタ**  >  **Verizon ネットワーク**] をクリックします。

2. [ **Verizon ネットワーク**製品の説明] ページで、[**コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[ **次へ**] をクリックします。
  
   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage のパスワードを入力します。

5. コネクタが作成されたら、ポップアップウィンドウを閉じて次のページに進むことができます。

6. [ **ユーザーマッピング** ] ページで、[ユーザーマッピングの自動設定] を有効にして、[ **次へ**] をクリックします。 カスタムマッピングが必要な場合は、CSV ファイルをアップロードし、[ **次へ**] をクリックします。

7. 管理者の同意を得てから、[ **次へ**] をクリックします。

   管理者の同意を得るには、Office 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

8. 設定内容を確認し、[ **完了** ] をクリックしてコネクタを作成します。

9. [ **データコネクタ** ] ページの [コネクタ] タブに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。

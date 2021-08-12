---
title: 基本的なモビリティとセキュリティの設定
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: デバイスをリモートでワイプするなどのアクションを実行して、ユーザーのモバイル デバイスをセキュリティで保護および管理するための基本モビリティとセキュリティを設定します。
ms.openlocfilehash: 9068594bdc4049336e87e3ed87ede9c4277f83fb0921d84b0b66099701aad91e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53826788"
---
# <a name="set-up-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの設定

Microsoft 365 用の組み込みの Basic Mobility and Security は、iPhone、iPad、Android、携帯電話などのユーザーのモバイル デバイスをセキュリティで保護および管理Windowsします。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

不明な点がある場合は、 一般的な質問に対処するためのよく寄せられる質問については、「Basic Mobility and Security に関するよく寄せられる質問 [(FAQ)」を参照してください](frequently-asked-questions.yml)。 委任された管理者アカウントを使用して Basic Mobility and Security を管理できないことに注意してください。 詳細については、「パートナー: [委任された管理を提供する」を参照してください](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。 

デバイス管理は、セキュリティ & コンプライアンス センターの一部なので、Basic Mobility and Security セットアップを開始するには、そこに移動する必要があります。

## <a name="activate-the-basic-mobility-and-security-service"></a>Basic Mobility and Security サービスをアクティブ化する

1. グローバル管理者アカウントMicrosoft 365にサインインします。

2. [基本モビリティと [セキュリティのアクティブ化] に移動します](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。

   Basic Mobility and Security をアクティブ化するには、時間がかかる場合があります。 完了すると、次に実行する手順を説明するメールが届きます。

## <a name="set-up-mobile-device-management"></a>モバイル デバイス管理のセットアップ

サービスの準備ができたら、次の手順を実行してセットアップを完了します。

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>手順 1: (必須) 基本モビリティとセキュリティのドメインを構成する

カスタム ドメインを Microsoft 365 に関連付けなかったり、Windows デバイスを管理していない場合は、このセクションを省略できます。 それ以外の場合は、DNS ホストでドメインの DNS レコードを追加する必要があります。 レコードを既に追加している場合は、Microsoft 365を使用してドメインを設定する一環として、すべて設定されます。 レコードを追加すると、カスタム ドメインを使用する電子メール アドレスを使用して Windows デバイスにサインインする組織内の Microsoft 365 ユーザーが、Basic Mobility and Security に登録するためにリダイレクトされます。

レコードのセットアップに関するヘルプが必要ですか? ドメイン レジストラーを検索し、レジストラー名を選択して、「ドメインに接続するための DNS レコードの追加」のリストで DNS レコードを作成するための詳細なヘルプに [移動します](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。 これらの手順を使用して、「登録を簡単にする」で説明されている CNAME[レコードWindows作成Azure AD Premium。](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

2 つの CNAME レコードを追加したら、セキュリティ & コンプライアンス センターに戻り、[データ損失防止デバイスの管理] に移動して次の手順  >     を完了します。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>手順 2: (必須) iOS デバイス用の APNs 証明書を構成する

iOS デバイス (iPad iPhone など) を管理するには、APNs 証明書を作成する必要があります。

1. グローバル管理者アカウントMicrosoft 365にサインインします。

2. ブラウザーの種類:  [https://protection.office.com](https://protection.office.com/) です。

3. [ **データ損失防止デバイス**   >  **の管理] を** 選択し **、[iOS デバイスの APNs 証明書] を選択します**。

4. [Apple プッシュ通知証明書] ページ設定[次へ] を **選択します**。

5. [CSR **ファイルをダウンロードする**] を選択し、覚えているコンピューターのどこかに証明書署名要求   を保存します。 [次 **へ] を選択します**。

6. [APNs 証明書の作成] ページで、次の設定を行います。

   - [Apple APNS ポータル] を選択して、Apple プッシュ証明書ポータルを開きます。
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - [証明書の作成] を選択し、利用規約に同意します。
   - コンピューターにダウンロードした証明書署名要求を [証明書] から参照Microsoft 365し、[アップロード] を選択します。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. [次へ] に戻Microsoft 365し、[次へ] を **選択します**。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. [完了  **] を選択します**。

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>手順 3: (推奨) 多要素認証のセットアップ

MFA は、2 番目の形式の認証をMicrosoft 365、モバイル デバイスの登録に必要なサインインをセキュリティで保護するのに役立ちます。 ユーザーは、仕事用アカウントのパスワードを正しく入力した後、モバイル デバイスで電話、テキスト メッセージ、アプリ通知を確認する必要があります。 この 2 番目の形式の認証が完了した後にのみ、デバイスを登録できます。 ユーザー デバイスが Basic Mobility and Security に登録された後、ユーザーは自分の仕事用アカウントMicrosoft 365リソースにアクセスできます。

Azure ADポータルで MFA を有効にする方法については、「多要素認証のセットアップ [」を参照してください](../security-and-compliance/set-up-multi-factor-authentication.md)。

MFA を設定した後、セキュリティ & コンプライアンス センターに戻り、[データ **** 損失防止デバイス管理デバイス ポリシー] に移動して、次   >     >  ****   の手順を完了します。

### <a name="step-4-recommended-manage-device-security-policies"></a>手順 4: (推奨) デバイス セキュリティ ポリシーの管理

次の手順では、デバイス セキュリティ ポリシーを作成して展開し、組織のデータを保護Microsoft 365します。 たとえば、ユーザーがデバイスを紛失した場合は、5 分間の非アクティブ状態の後にデバイスをロックし、3 回サインインが失敗した後にデバイスをワイプするポリシーを作成することで、データ損失を防ぐのに役立ちます。

1. グローバル管理者アカウントMicrosoft 365にサインインします。

2. [モバイル [デバイス管理のアクティブ化] を選択します](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。 サービスがアクティブ化されている場合は、代わりにライセンス認証手順に[デバイスの管理] へのリンク [が表示されます](https://admin.microsoft.com/adminportal/home#/MifoDevices)   。

3. [デバイス ポリシー **] に移動します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティポリシーとモビリティ ポリシー設定":::

4. 「Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成」の手順に従って、組織に適したデバイス セキュリティ ポリシーを作成して [展開します](create-device-security-policies.md)。

> [!TIP]
>
> - 新しいポリシーを作成する場合は、ユーザー デバイスがポリシーに準拠していないアクセスを許可し、ポリシー違反を報告するポリシーを設定できます。 これにより、ポリシーの影響を受け取るモバイル デバイスの数を確認し、ポリシーへのアクセスをブロックMicrosoft 365。
>
> - 組織内のすべてのユーザーに新しいポリシーを展開する前に、少人数のユーザーが使用するデバイスでテストすることをお勧めします。
>
> - また、ポリシーを展開する前に、Basic Mobility and Security にデバイスを登録する場合の潜在的な影響を組織に知らせる必要があります。 ポリシーの設定方法によっては、ポリシーに準拠していないデバイス (非準拠デバイス) がポリシーへのアクセスをブロックMicrosoft 365。 非準拠のデバイスには、アプリ、写真、その他の個人情報がインストールされている場合もあります。デバイスがワイプされた場合、登録されているデバイス上で削除される可能性があります。 詳細については、「Basic [Mobility and Security でモバイル デバイスをワイプする」を参照してください](wipe-mobile-device.md)。

## <a name="make-sure-users-enroll-their-devices"></a>ユーザーがデバイスを登録する

モバイル デバイス管理ポリシーを作成して展開した後、デバイス ポリシーが適用される組織内のライセンスを取得した Microsoft 365 ユーザーは、次回モバイル デバイスから Microsoft 365 にサインインすると、登録メッセージを受け取ります。 電子メールとドキュメントにアクセスする前に、登録とライセンス認証Microsoft 365必要があります。 詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。

> [!IMPORTANT]
> ユーザーの優先言語が登録プロセスでサポートされていない場合、ユーザーは別の言語でモバイル デバイスの登録通知と手順を受け取る可能性があります。 モバイル デバイスでの登録プロセスで現在Microsoft 365サポートされている言語は一部ではありません。

Android または iOS デバイスを使用しているユーザーは、登録プロセスのポータル サイトアプリをインストールする必要があります。

## <a name="related-content"></a>関連コンテンツ

[基本モビリティとセキュリティの機能](capabilities.md) (記事)\
[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md) (記事)
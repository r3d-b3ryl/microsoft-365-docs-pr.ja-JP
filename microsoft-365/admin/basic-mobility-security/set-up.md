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
search.appverid:
- MET150
description: Basic Mobility and Security をセットアップして、ユーザーのモバイル デバイスをセキュリティで保護および管理します。
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876866"
---
# <a name="set-up-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの設定

Microsoft 365 に組み込みの Basic Mobility and Security を使用すると、iPhone、iPad、Android、Windows スマートフォンなどのユーザーのモバイル デバイスをセキュリティで保護および管理できます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

質問がおありですか? よく寄せられる質問の解決に役立つ FAQ については [、「Basic Mobility and Security に関するよく寄せられる質問 (FAQ)」を参照してください](frequently-asked-questions.md)。 委任された管理者アカウントを使用して Basic Mobility and Security を管理することはできません。 詳しくは、「パートナー: 代理管理 [を提供する」をご覧ください](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。 

デバイス管理はセキュリティ & コンプライアンス センターの一部なので、Basic Mobility and Security のセットアップを開始するには、そこに移動する必要があります。

## <a name="activate-the-basic-mobility-and-security-service"></a>Basic Mobility and Security サービスをアクティブ化する

1. グローバル管理者アカウントで Microsoft 365 にサインインします。

2. [Basic [Mobility and Security のアクティブ化] に移動します](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。

   Basic Mobility and Security をアクティブ化するには、少し時間がかかる場合があります。 完了すると、次の手順を説明するメールが届きます。

## <a name="set-up-mobile-device-management"></a>モバイル デバイス管理をセットアップする

サービスの準備ができたら、次の手順を実行してセットアップを完了します。

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>手順 1: (必須) Basic Mobility and Security のドメインを構成する

Microsoft 365 に関連付けられているカスタム ドメインを持たなかったり、Windows デバイスを管理していない場合は、このセクションを省略できます。 それ以外の場合は、DNS ホストでドメインの DNS レコードを追加する必要があります。 Microsoft 365 でドメインを設定する一環として、レコードを既に追加している場合は、すべて設定されています。 レコードを追加すると、カスタム ドメインを使用するメール アドレスを使用して Windows デバイスにサインインする組織内の Microsoft 365 ユーザーは、Basic Mobility and Security への登録にリダイレクトされます。

レコードの設定に関するヘルプが必要な場合 ドメイン レジストラーを検索し、レジストラー名を選択して、「ドメインに接続するための DNS レコードの追加」の一覧で DNS レコードを作成するための詳細なヘルプに [移動します](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。 これらの手順を使用して、「Azure AD Premium を使用せずに Windows 登録を簡略化する」で説明されている CNAME [レコードを作成します](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)。

2 つの CNAME レコードを追加した後、Security & コンプライアンス センターに戻り、データ損失防止デバイス管理に移動して、次の手順  >     を完了します。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>手順 2: (必須) iOS デバイス用の APNs 証明書を構成する

iPad や iPhone のような iOS デバイスを管理するには、APNs 証明書を作成する必要があります。

1. グローバル管理者アカウントで Microsoft 365 にサインインします。

2. ブラウザーで次の種類を入力します  [https://protection.office.com](https://protection.office.com/) 。

3. [ **データ損失防止デバイス**   >  **管理] を選択し**、[iOS デバイスの **APNs 証明書] を選択します**。

4. On the Apple Push Notification Certificate Settings page, choose **Next**.

5. [CSR **ファイルのダウンロード] を** 選択し、コンピューター上の任意の場所に証明書署名要求を   保存します。 [次へ **] を選択します**。

6. [APNs 証明書の作成] ページで、次の設定を行います。

   - Apple APNS ポータルを選択して、Apple Push Certificates Portal を開きます。
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - [証明書の作成] を選択し、使用条件に同意します。
   - Microsoft 365 からコンピューターにダウンロードした証明書署名要求を参照し、Upload を選択します。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365 に戻り、[次へ] を選択 **します**。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. [完了]  **を選択します**。

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>手順 3: (推奨) 多要素認証を設定する

MFA は、2 番目の認証形式を必要とすることで、モバイル デバイス登録用に Microsoft 365 へのサインインをセキュリティで保護します。 ユーザーは、仕事用アカウントのパスワードを正しく入力した後、モバイル デバイスで電話、テキスト メッセージ、またはアプリの通知を確認する必要があります。 この 2 番目の形式の認証が完了した後にのみ、デバイスを登録できます。 ユーザー デバイスを Basic Mobility and Security に登録すると、ユーザーは自分の仕事用アカウントのみを使用して Microsoft 365 リソースにアクセスできます。

Azure AD ポータルで MFA を有効にする方法については、「多要素認証の [セットアップ」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=519255)。

MFA を設定したら、& セキュリティ/コンプライアンス センターに戻り、データ損失 **** 防止デバイス管理デバイス ポリシーに移動して、次の手順   >     >  ****   を完了します。

### <a name="step-4-recommended-manage-device-security-policies"></a>手順 4: (推奨) デバイス セキュリティ ポリシーを管理する

次の手順では、Microsoft 365 組織データの保護に役立つデバイス セキュリティ ポリシーを作成して展開します。 たとえば、5 分間の非アクティブ状態の後にデバイスをロックし、3 回のサインイン失敗後にデバイスをワイプするポリシーを作成することで、ユーザーがデバイスを紛失した場合のデータ損失を防ぐのに役立ちます。

1. グローバル管理者アカウントで Microsoft 365 にサインインします。

2. [モバイル [デバイス管理のアクティブ化] を選択します](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。 サービスがアクティブ化されている場合は、代わりにライセンス認証の手順を実行すると、[デバイスの管理] へのリンク [が表示されます](https://admin.microsoft.com/adminportal/home#/MifoDevices)   。

3. [デバイス ポリシー **] に移動します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティとモビリティのポリシー設定":::

4. 「Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成」の手順に従って、組織に適したデバイス セキュリティ ポリシーを作成して [展開します](create-device-security-policies.md)。

> [!TIP]
>
> - 新しいポリシーを作成するときに、ユーザー デバイスがポリシーに準拠していない場合に、アクセスを許可し、ポリシー違反を報告するポリシーを設定できます。 これにより、Microsoft 365 へのアクセスをブロックすることなく、ポリシーの影響を受け取るモバイル デバイスの数を確認できます。
>
> - 組織内のすべてのユーザーに新しいポリシーを展開する前に、小規模なユーザーが使用するデバイスでテストすることをお勧めします。
>
> - また、ポリシーを展開する前に、Basic Mobility and Security にデバイスを登録する場合の潜在的な影響を組織に知らせる必要があります。 ポリシーの設定方法によっては、ポリシーに準拠していないデバイス (非準拠デバイス) が Microsoft 365 へのアクセスをブロックされる可能性があります。 非準拠デバイスには、アプリ、写真、その他の個人情報がインストールされている場合もあります。登録されているデバイスでは、デバイスがワイプされた場合に削除される可能性があります。 詳細については [、「Basic Mobility and Security」の「モバイル デバイスをワイプする」を参照してください](wipe-mobile-device.md)。

## <a name="make-sure-users-enroll-their-devices"></a>ユーザーが自分のデバイスを登録する

モバイル デバイス管理ポリシーを作成して展開すると、デバイス ポリシーが適用される組織内のライセンスを取得した各 Microsoft 365 ユーザーは、次回モバイル デバイスから Microsoft 365 にサインインすると、登録メッセージを受け取ります。 Microsoft 365 のメールとドキュメントにアクセスするには、登録とライセンス認証の手順を完了する必要があります。 詳細については [、「Basic Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。

> [!IMPORTANT]
> 登録プロセスでユーザーの優先言語がサポートされていない場合、ユーザーはモバイル デバイスの登録通知と手順を別の言語で受け取る可能性があります。 Microsoft 365 でサポートされている言語の中には、モバイル デバイスでの登録プロセスが現在サポートされていないものがあります。

Android または iOS デバイスを使用するユーザーは、登録プロセスの一環としてポータル サイト アプリをインストールする必要があります。

## <a name="related-topics"></a>関連項目

[基本的なモビリティとセキュリティの機能](capabilities.md)<br/>
[Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成](create-device-security-policies.md)
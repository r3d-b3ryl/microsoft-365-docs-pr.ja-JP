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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: デバイスをリモートワイプするなどの操作を実行して、ユーザーのモバイル デバイスをセキュリティで保護および管理するように Basic Mobility と Security を設定します。
ms.openlocfilehash: b26906c0f374f5dc103fe26e4619663195da6ebd
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780833"
---
# <a name="set-up-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの設定

Microsoft 365用の組み込みの Basic Mobility and Security は、iPhone、iPad、Android、Windowsスマートフォンなどのユーザーのモバイル デバイスをセキュリティで保護し、管理するのに役立ちます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

不明な点がある場合は、 一般的な質問に対処するための FAQ については、「 [基本的なモビリティとセキュリティに関してよく寄せられる質問 (FAQ)」](frequently-asked-questions.yml)を参照してください。 委任された管理者アカウントを使用して基本的なモビリティとセキュリティを管理することはできません。 詳細については、「 [パートナー: 委任された管理を提供する](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)」を参照してください。 

デバイス管理はセキュリティ & コンプライアンス センターの一部であるため、基本的なモビリティとセキュリティのセットアップを開始するためにそこに移動する必要があります。

## <a name="activate-the-basic-mobility-and-security-service"></a>Basic Mobility and Security サービスをアクティブ化する

1. グローバル管理者アカウントでMicrosoft 365にサインインします。

2. [[Basic Mobility and Security のアクティブ化]](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) に移動します。

   Basic Mobility and Security のアクティブ化には時間がかかる場合があります。 完了すると、次の手順を説明する電子メールが届きます。

## <a name="set-up-mobile-device-management"></a>モバイル デバイス管理を設定する

サービスの準備ができたら、次の手順を実行してセットアップを完了します。

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>手順 1: (必須) Basic Mobility and Security のドメインを構成する

Microsoft 365に関連付けられているカスタム ドメインがない場合、またはデバイスWindows管理していない場合は、このセクションをスキップできます。 それ以外の場合は、DNS ホストでドメインの DNS レコードを追加する必要があります。 Microsoft 365を使用してドメインを設定する一環として、レコードを既に追加した場合は、すべて設定されます。 レコードを追加すると、カスタム ドメインを使用する電子メール アドレスを使用して自分のWindows デバイスにサインインする組織内のMicrosoft 365ユーザーがリダイレクトされ、Basic Mobility と Security に登録されます。

レコードのセットアップに関するヘルプが必要ですか? ドメイン レジストラーを検索し、レジストラー名を選択して、「DNS レコードを追加してドメインに接続する」の一覧で [DNS レコード](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)を作成するための詳細なヘルプに移動します。 これらの手順を使用して、「[Azure AD Premiumなしで登録Windows簡略化する](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)」で説明されている CNAME レコードを作成します。

2 つの CNAME レコードを追加したら、セキュリティ & コンプライアンス センターに戻り、 **データ損失防止** > **デバイス管理** に移動して次の手順を完了します。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>手順 2: (必須) iOS デバイス用の APNs 証明書を構成する

iPadや iPhone などの iOS デバイスを管理するには、APN 証明書を作成する必要があります。

1. グローバル管理者アカウントでMicrosoft 365にサインインします。

2. ブラウザーの種類: [https://protection.office.com](https://protection.office.com/).

3. **[データ損失防止** > **デバイス管理**] を選択し、[**iOS デバイス用の APNs 証明書] を選択します**。

4. [Apple プッシュ通知証明書設定] ページで、[**次へ**] を選択します。

5. [ **CSR ファイルのダウンロード** ] を選択し、証明書署名要求を覚えているコンピューターのどこかに保存します。 **[次へ]** を選択します。

6. [APNs 証明書の作成] ページで、次の手順を実行します。

   - Select Apple APNS Portal to open the Apple Push Certificates Portal. 
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Select Create a Certificate and accept the Terms of Use.
   - Microsoft 365からコンピューターにダウンロードした証明書署名要求に移動し、アップロードを選択します。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365に戻るし、[**次へ**] を選択します。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. **[完了]** を選択します。

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>手順 3: (推奨) 多要素認証を設定する

MFA は、2 番目の形式の認証を必要とすることで、モバイル デバイス登録のMicrosoft 365へのサインインをセキュリティで保護するのに役立ちます。 ユーザーは、職場アカウントのパスワードを正しく入力した後、モバイル デバイスで電話、テキスト メッセージ、またはアプリの通知を確認する必要があります。 この 2 番目の形式の認証が完了した後にのみ、デバイスを登録できます。 ユーザー デバイスが Basic Mobility and Security に登録されると、ユーザーは自分の職場アカウントでのみMicrosoft 365リソースにアクセスできます。

Azure AD ポータルで MFA を有効にする方法については、「[多要素認証を設定](../security-and-compliance/set-up-multi-factor-authentication.md)する」を参照してください。

MFA を設定したら、セキュリティ & コンプライアンス センターに戻り、**Data loss preventionDevice** >  **managementDevice** >  **ポリシー** に移動して次の手順を完了します。

### <a name="step-4-recommended-manage-device-security-policies"></a>手順 4: (推奨) デバイス セキュリティ ポリシーを管理する

次の手順では、デバイス セキュリティ ポリシーを作成して展開し、Microsoft 365組織のデータを保護します。 たとえば、ユーザーがデバイスを紛失した場合にデータ損失を防ぐには、5 分間の非アクティブ状態の後にデバイスをロックし、3 回のサインイン エラーの後にデバイスをワイプするポリシーを作成します。

1. グローバル管理者アカウントでMicrosoft 365にサインインします。

2. [[モバイル デバイス管理のアクティブ化](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)] を選択します。 サービスがアクティブ化されている場合は、代わりにアクティブ化の手順に従って、[ [デバイスの管理]](https://admin.microsoft.com/adminportal/home#/MifoDevices) へのリンクが表示されます。

3. **デバイス ポリシー** に移動します。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティとモビリティのポリシー設定。":::

4. 「基本的なモビリティとセキュリティでデバイス セキュリティ ポリシーを作成する」の手順に従って、組織に適した [デバイス セキュリティ ポリシーを作成して展開します](create-device-security-policies.md)。

> [!TIP]
>
> - 新しいポリシーを作成するときに、ユーザー デバイスがポリシーに準拠していない場合に、ポリシー違反へのアクセスを許可し、ポリシー違反を報告するようにポリシーを設定できます。 これにより、Microsoft 365へのアクセスをブロックすることなく、ポリシーの影響を受けるモバイル デバイスの数を確認できます。
>
> - 組織内のすべてのユーザーに新しいポリシーを展開する前に、少数のユーザーが使用するデバイスでテストすることをお勧めします。
>
> - また、ポリシーを展開する前に、基本的なモビリティとセキュリティにデバイスを登録することによる潜在的な影響を組織に知らせます。 ポリシーの設定方法によっては、ポリシーに準拠していないデバイス (非準拠デバイス) がMicrosoft 365へのアクセスをブロックされる可能性があります。 非準拠デバイスには、アプリがインストールされている場合もあります。写真、その他の個人情報は、デバイスがワイプされた場合に、登録されているデバイス上で削除される可能性があります。 詳細については、「 [Basic Mobility and Security でモバイル デバイスをワイプする](wipe-mobile-device.md)」を参照してください。

## <a name="make-sure-users-enroll-their-devices"></a>ユーザーがデバイスを登録していることを確認する

モバイル デバイス管理ポリシーを作成して展開した後、デバイス ポリシーが適用される組織内のライセンスMicrosoft 365ユーザーは、次回モバイル デバイスからMicrosoft 365にサインインするときに登録メッセージを受け取ります。 電子メールやドキュメントにアクセスする前に、登録とアクティブ化の手順Microsoft 365完了する必要があります。 詳細については、「 [Basic Mobility and Security を使用してモバイル デバイスを登録する」](enroll-your-mobile-device.md)を参照してください。

> [!IMPORTANT]
> ユーザーの優先言語が登録プロセスでサポートされていない場合、ユーザーは別の言語でモバイル デバイスで登録通知と手順を受け取る可能性があります。 Microsoft 365でサポートされているすべての言語が、モバイル デバイスでの登録プロセスで現在サポートされているわけではありません。

Android または iOS デバイスを持つユーザーは、登録プロセスの一環としてポータル サイト アプリをインストールする必要があります。

## <a name="related-content"></a>関連コンテンツ

[Basic Mobility and Security の機能](capabilities.md) (記事)\
[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md) (記事)

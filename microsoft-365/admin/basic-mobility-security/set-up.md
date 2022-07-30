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
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: デバイスをリモートワイプするなどの操作を実行して、ユーザーのモバイル デバイスをセキュリティで保護および管理するように Basic Mobility と Security を設定します。
ms.openlocfilehash: 0658db2546a72cc35da79e396af42ae54e23e6a7
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084435"
---
# <a name="set-up-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの設定

組み込みの Basic Mobility and Security for Microsoft 365 は、iPhone、iPad、Android、Windows スマートフォンなどのユーザーのモバイル デバイスのセキュリティと管理に役立ちます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

不明な点がある場合は、 一般的な質問に対処するための FAQ については、「 [基本的なモビリティとセキュリティに関してよく寄せられる質問 (FAQ)」](frequently-asked-questions.yml)を参照してください。 委任された管理者アカウントを使用して基本的なモビリティとセキュリティを管理することはできません。 詳細については、「 [パートナー: 委任された管理を提供する](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)」を参照してください。 

デバイス管理はセキュリティ & コンプライアンス センターの一部であるため、基本的なモビリティとセキュリティのセットアップを開始するためにそこに移動する必要があります。

## <a name="activate-the-basic-mobility-and-security-service"></a>Basic Mobility and Security サービスをアクティブ化する

1. グローバル管理者アカウントを使用して Microsoft 365 にサインインします。

2. [[Basic Mobility and Security のアクティブ化]](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) に移動します。

   Basic Mobility and Security のアクティブ化には時間がかかる場合があります。 完了すると、次の手順を説明する電子メールが届きます。

## <a name="set-up-mobile-device-management"></a>モバイル デバイス管理を設定する

サービスの準備ができたら、次の手順を実行してセットアップを完了します。

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>手順 1: (必須) Basic Mobility and Security のドメインを構成する

Microsoft 365 に関連付けられているカスタム ドメインがない場合、または Windows デバイスを管理していない場合は、このセクションをスキップできます。 それ以外の場合は、DNS ホストでドメインの DNS レコードを追加する必要があります。 Microsoft 365 を使用してドメインを設定する一環として、レコードを既に追加した場合は、すべて設定されます。 レコードを追加すると、カスタム ドメインを使用する電子メール アドレスを使用して Windows デバイスにサインインする組織内の Microsoft 365 ユーザーが、Basic Mobility and Security に登録するようにリダイレクトされます。

レコードのセットアップに関するヘルプが必要ですか? ドメイン レジストラーを検索し、レジストラー名を選択して、「DNS レコードを追加してドメインに接続する」の一覧で [DNS レコード](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)を作成するための詳細なヘルプに移動します。 これらの手順を使用して、「 [Azure AD Premium を使用せずに Windows 登録を簡略化する](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)」で説明されている CNAME レコードを作成します。

2 つの CNAME レコードを追加したら、セキュリティ & コンプライアンス センターに戻り、 **データ損失防止** > **デバイス管理** に移動して次の手順を完了します。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>手順 2: (必須) iOS デバイス用の APNs 証明書を構成する

iPad や iPhone などの iOS デバイスを管理するには、APN 証明書を作成する必要があります。

1. グローバル管理者アカウントを使用して Microsoft 365 にサインインします。

2. [Microsoft 365 管理センター](https://portal.office.com/adminportal/home?#/MifoDevices)に移動し、**iOS 用の APNs 証明書を** 選択します。

4. [Apple プッシュ通知証明書の設定] ページで、[ **次へ**] を選択します。

5. [ **CSR ファイルのダウンロード** ] を選択し、証明書署名要求を覚えているコンピューターのどこかに保存します。 **[次へ]** を選択します。

6. [APNs 証明書の作成] ページで、次の手順を実行します。

   - Select Apple APNS Portal to open the Apple Push Certificates Portal. 
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Select Create a Certificate and accept the Terms of Use.
   - Microsoft 365 からコンピューターにダウンロードした証明書署名要求に移動し、SelectUpload を選択します。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365 に戻るし、[**次へ**] を選択します。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. **[完了]** を選択します。

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>手順 3: (推奨) 多要素認証を設定する

MFA は、2 番目の形式の認証を必要とすることで、モバイル デバイス登録のために Microsoft 365 へのサインインをセキュリティで保護するのに役立ちます。 ユーザーは、職場アカウントのパスワードを正しく入力した後、モバイル デバイスで電話、テキスト メッセージ、またはアプリの通知を確認する必要があります。 この 2 番目の形式の認証が完了した後にのみ、デバイスを登録できます。 ユーザー デバイスが Basic Mobility and Security に登録されると、ユーザーは自分の職場アカウントだけで Microsoft 365 リソースにアクセスできます。

Azure AD portal で MFA を有効にする方法については、「 [多要素認証を設定](../security-and-compliance/set-up-multi-factor-authentication.md)する」を参照してください。

MFA を設定したら、セキュリティ & コンプライアンス センターに戻り、 **データ損失防止** > **デバイス管理** > **デバイス ポリシー** に移動して、次の手順を完了します。

### <a name="step-4-recommended-manage-device-security-policies"></a>手順 4: (推奨) デバイス セキュリティ ポリシーを管理する

次の手順では、Microsoft 365 組織のデータを保護するためにデバイス セキュリティ ポリシーを作成して展開します。 たとえば、ユーザーがデバイスを紛失した場合にデータ損失を防ぐには、5 分間の非アクティブ状態の後にデバイスをロックし、3 回のサインイン エラーの後にデバイスをワイプするポリシーを作成します。

1. グローバル管理者アカウントを使用して Microsoft 365 にサインインします。

2. [[モバイル デバイス管理のアクティブ化](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)] を選択します。 サービスがアクティブ化されている場合は、代わりにアクティブ化の手順に従って、[ [デバイスの管理]](https://admin.microsoft.com/adminportal/home#/MifoDevices) へのリンクが表示されます。

3. **デバイス ポリシー** に移動します。

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="基本的なセキュリティとモビリティのポリシー設定。":::

4. 「基本的なモビリティとセキュリティでデバイス セキュリティ ポリシーを作成する」の手順に従って、組織に適した [デバイス セキュリティ ポリシーを作成して展開します](create-device-security-policies.md)。

> [!TIP]
>
> - 新しいポリシーを作成するときに、ユーザー デバイスがポリシーに準拠していない場合に、ポリシー違反へのアクセスを許可し、ポリシー違反を報告するようにポリシーを設定できます。 これにより、Microsoft 365 へのアクセスをブロックすることなく、ポリシーの影響を受けるモバイル デバイスの数を確認できます。
>
> - 組織内のすべてのユーザーに新しいポリシーを展開する前に、少数のユーザーが使用するデバイスでテストすることをお勧めします。
>
> - また、ポリシーを展開する前に、基本的なモビリティとセキュリティにデバイスを登録することによる潜在的な影響を組織に知らせます。 ポリシーの設定方法によっては、ポリシーに準拠していないデバイス (非準拠デバイス) が Microsoft 365 へのアクセスをブロックされる可能性があります。 非準拠デバイスには、アプリがインストールされている場合もあります。写真、その他の個人情報は、デバイスがワイプされた場合に、登録されているデバイス上で削除される可能性があります。 詳細については、「 [Basic Mobility and Security でモバイル デバイスをワイプする](wipe-mobile-device.md)」を参照してください。

## <a name="make-sure-users-enroll-their-devices"></a>ユーザーがデバイスを登録していることを確認する

モバイル デバイス管理ポリシーを作成して展開すると、デバイス ポリシーが適用される組織内のライセンスを持つ各 Microsoft 365 ユーザーは、次にモバイル デバイスから Microsoft 365 にサインインするときに登録メッセージを受け取ります。 Microsoft 365 の電子メールとドキュメントにアクセスするには、登録とアクティブ化の手順を完了する必要があります。 詳細については、「 [Basic Mobility and Security を使用してモバイル デバイスを登録する」](enroll-your-mobile-device.md)を参照してください。

> [!IMPORTANT]
> ユーザーの優先言語が登録プロセスでサポートされていない場合、ユーザーは別の言語でモバイル デバイスで登録通知と手順を受け取る可能性があります。 Microsoft 365 でサポートされているすべての言語が、モバイル デバイスでの登録プロセスで現在サポートされているわけではありません。

Android または iOS デバイスを持つユーザーは、登録プロセスの一環としてポータル サイト アプリをインストールする必要があります。

## <a name="related-content"></a>関連コンテンツ

[Basic Mobility and Security の機能](capabilities.md) (記事)\
[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md) (記事)

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
description: ユーザーのモバイルデバイスをセキュリティで保護して管理するための基本的なモビリティとセキュリティを設定します。
ms.openlocfilehash: 079593381d6395c18cd80f3eeab2e16837a2d27a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545810"
---
# <a name="set-up-basic-mobility-and-security"></a>基本的なモビリティとセキュリティの設定

Microsoft 365 の組み込みの基本的なモビリティとセキュリティにより、iPhones、Ipad、Androids、Windows phone などのユーザーのモバイルデバイスをセキュリティで保護し、管理することができます。 デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。

質問がおありですか? よく寄せられる質問については、「 [基本的なモビリティおよびセキュリティに関する faq (faq)](frequently-asked-questions.md)」を参照してください。 委任された管理者アカウントを使用して、基本的なモビリティとセキュリティを管理することはできないことに注意してください。 詳細については、「 [パートナー: 代理管理を提案](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)する」を参照してください。 

デバイス管理はセキュリティ & コンプライアンスセンターの一部であるため、MDM セットアップを開始するには、このページに移動する必要があります。

## <a name="activate-the-basic-mobility-and-security-service"></a>基本的なモビリティおよびセキュリティサービスをアクティブ化する

1. グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。

2. [ [基本的なモビリティとセキュリティをアクティブ](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)にする] に移動します。

   基本的なモビリティとセキュリティをアクティブにするには、しばらく時間がかかる場合があります。 完了すると、次の手順について説明する電子メールが届きます。

## <a name="set-up-mobile-device-management"></a>モバイルデバイス管理の設定

サービスの準備ができたら、次の手順を実行してセットアップを完了します。

### <a name="step-1-required-configure-domains-for-mdm"></a>手順 1: (必須) MDM のドメインを構成する

Microsoft 365 に関連付けられたカスタムドメインがない場合、または Windows デバイスを管理していない場合は、このセクションを省略できます。 それ以外の場合は、DNS ホストでドメインの DNS レコードを追加する必要があります。 Microsoft 365 を使用したドメインのセットアップの一環としてレコードを既に追加している場合は、すべての設定が完了しています。 レコードを追加すると、組織内の Microsoft 365 ユーザーが、カスタムドメインを使用する電子メールアドレスを使用して Windows デバイスにサインインすると、基本的なモビリティとセキュリティに登録されます。

レコードの設定に関するヘルプが必要な場合 ドメインレジストラーを見つけて、dns レコードを追加するための手順を、「 [ドメインを接続するために dns レコードを追加する](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」に記載されている一覧に表示されるように、レジストラー名を選択します。 これらの手順を使用して、「 [AZURE AD Premium を使用しない Windows 登録を簡素化](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)する」で説明されている CNAME レコードを作成します。

2つの CNAME レコードを追加したら、セキュリティ & コンプライアンスセンターに戻り、[**データ損失防止**デバイスの管理] に移動して  >  **Device management**   次の手順を完了します。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>手順 2: (必須) iOS デバイス用の APNs 証明書を構成する

IPad や iPhones などの iOS デバイスを管理するには、APNs 証明書を作成する必要があります。

1. グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。

2. ブラウザーで、次のように入力  [https://protection.office.com](https://protection.office.com/) します。

3. [ **データ損失防止**   >  **デバイス管理**] を選択し、 **iOS デバイス用の APNs 証明書**を選択します。

4. [Apple プッシュ通知の証明書の設定] ページで、[ **次へ**] をクリックします。

5. [ **CSR ファイルをダウンロード**   し、証明書の署名要求をコンピューターのどこかに保存する] を選択して、覚えておきます。 [ **次へ**] を選択します。

6. [APNs 証明書の作成] ページで、次のようにします。

   - Apple APNS Portal を選択して、Apple プッシュ証明書ポータルを開きます。
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - [証明書を作成し、使用条件に同意します] を選択します。
   - Microsoft 365 からコンピューターにダウンロードした証明書の署名要求を参照し、選択します。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365 に戻って、[ **次へ**] を選択します。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. [  **完了**] を選択します。

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>手順 3: (推奨) 多要素認証をセットアップする

MFA は、2番目の形式の認証を必要とすることで、モバイルデバイスの登録用に Microsoft 365 へのサインインをセキュリティで保護します。 ユーザーは、職場のアカウントパスワードを正しく入力した後に、モバイルデバイスでの電話、テキストメッセージ、アプリの通知を確認する必要があります。 この2番目の形式の認証が完了した後にのみ、デバイスを登録できます。 ユーザーデバイスが基本的なモビリティとセキュリティに登録されると、ユーザーは職場アカウントのみを使用して Microsoft 365 リソースにアクセスできるようになります。

Azure AD ポータルで MFA を有効にする方法については、「 [多要素認証をセットアップ](https://go.microsoft.com/fwlink/p/?LinkId=519255)する」を参照してください。

MFA を設定したら、セキュリティ & コンプライアンスセンターに戻り、[ **データ損失防止**の   >  **デバイス管理**デバイスポリシー] に移動して   >  **Device policies**   次の手順を完了します。

### <a name="step-4-recommended-manage-device-security-policies"></a>手順 4: (推奨) デバイスセキュリティポリシーの管理

次の手順では、Microsoft 365 組織のデータを保護するために、デバイスのセキュリティポリシーを作成して展開します。 たとえば、ユーザーがデバイスを失った場合のデータ損失を防止するには、5分間非アクティブなデバイスをロックするポリシーを作成し、3回のサインインに失敗した後でデバイスをワイプします。

1. グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。

2. [ [モバイルデバイス管理のアクティブ化](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)] を選択します。 サービスがアクティブになっている場合は、代わりにアクティブ化の手順で [デバイスを管理](https://admin.microsoft.com/adminportal/home#/MifoDevices)するためのリンクが表示され   ます。

3. [ **デバイスポリシー**] に移動します。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティとモビリティのポリシー設定":::

4. 「 [Basic Mobility And security でのデバイスセキュリティポリシーの作成](create-device-security-policies.md)」の手順に従って、組織に適したデバイスセキュリティポリシーを作成して展開します。

> [!TIP]
>
> - 新しいポリシーを作成するときに、ユーザーデバイスがポリシーに準拠していない場合にアクセスを許可し、ポリシー違反を報告するようにポリシーを設定することができます。 これにより、Microsoft 365 へのアクセスをブロックすることなく、ポリシーによって影響を受けるモバイルデバイスの数を確認できます。
>
> - 組織内のすべてのユーザーに新しいポリシーを展開する前に、少数のユーザーが使用しているデバイスでテストすることをお勧めします。
>
> - また、ポリシーを展開する前に、組織は基本的なモビリティとセキュリティでデバイスを登録することによる潜在的な影響を把握しておきます。 ポリシーの設定方法によっては、ポリシーに準拠していないデバイス (準拠していないデバイス) が Microsoft 365 へのアクセスをブロックされることがあります。 準拠していないデバイスには、デバイスがワイプされている場合に、登録済みデバイス上にインストールされているアプリ、写真、その他の個人情報が含まれることもあります。 詳細については、「 [Basic Mobility And Security でモバイルデバイスをワイプする](wipe-mobile-device.md)」を参照してください。

## <a name="make-sure-users-enroll-their-devices"></a>ユーザーが自分のデバイスを登録していることを確認する

モバイルデバイス管理ポリシーを作成して展開した後、デバイスポリシーが適用する、組織内のライセンスが付与された各 Microsoft 365 ユーザーは、モバイルデバイスから Microsoft 365 に次回サインインしたときに登録メッセージを受け取ります。 Microsoft 365 の電子メールとドキュメントにアクセスする前に、登録とライセンス認証の手順を完了する必要があります。 詳細については、「 [Basic Mobility And Security を使用してモバイルデバイスを登録する](enroll-your-mobile-device.md)」を参照してください。

> [!IMPORTANT]
> 登録プロセスでユーザーの優先言語がサポートされていない場合、ユーザーは自分のモバイルデバイスで登録通知と手順を別の言語で受信する可能性があります。 Microsoft 365 でサポートされている言語の中には、現在、モバイルデバイスでの登録プロセスがサポートされていないものがあります。

Android または iOS デバイスを使用しているユーザーは、登録プロセスの一環として、ポータルサイトアプリをインストールする必要があります。

## <a name="related-topics"></a>関連項目

[基本的なモビリティとセキュリティの機能](capabilities.md)<br/>
[基本的なモビリティとセキュリティでデバイスのセキュリティポリシーを作成する](create-device-security-policies.md)
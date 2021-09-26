---
title: セットアップ制限のあるドメイン レジストラー
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
ROBOTS: NOINDEX
description: ドメイン レジストラーの中には、限定的なサービスを提供するものもあり、すべての Microsoft 機能がすべてのドメインで使えるわけではありません。
ms.openlocfilehash: 7fe6b047773e47964b5a00728b8c1443bdeef36e
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774594"
---
# <a name="domain-registrars-with-setup-limitations"></a>セットアップ制限のあるドメイン レジストラー

[DNSMadeEasy で Microsoft用の DNS レコードを作成する](#create-dns-records-at-dnsmadeeasy-for-microsoft)\
[Microsoft 用の easyDNS で DNS レコードを作成する](#create-dns-records-at-easydns-for-microsoft)\
[Freenom で Microsoft 用の DNS レコードを作成する](#create-dns-records-at-freenom-for-microsoft)\
[Microsoft 用の MyDomain で DNS レコードを作成する](#create-dns-records-at-mydomain-for-microsoft)\
[Windows ベースの DNS を使って Microsoft の DNS レコードを作成する](#create-dns-records-for-microsoft-using-windows-based-dns)\
[Google がドメインを管理している場合に DNS レコードを作成する (eNom)](#create-dns-records-when-your-domain-is-managed-by-google-enom)\
[Microsoft 用の 1&1 IONOS fで DNS レコードを作成する](#create-dns-records-at-11-ionos-for-microsoft)

ドメイン レジストラーの中には、サービスにかなりの制限があるものもあり、すべての Microsoft 機能がすべてのドメインで使えるわけではありません。 この記事では、一部のレジストラーの具体的な制限事項を紹介します。 

## <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>DNSMadeEasy で Microsoft 用の DNS レコードを作成する

DNSMadeEasy アカウントの場合、追加したドメインは、別のドメイン レジストラーから購入したものです。 DNSMadeEasy はドメイン登録サービスを提供していません。 DNSMadeEasy にログインして DNS レコードを作成できれば、所有していることが十分に証明されたことになります。

## <a name="create-dns-records-at-easydns-for-microsoft"></a>Microsoft 用の easyDNS で DNS レコードを作成する

SRV レコードは現在、easyDNS サービス パッケージではご利用いただけません。 easyDNS を含む高次のサービス レベルにアップグレードして、Teams に必要な SRV レコードに追加することが必要な場合があります。

## <a name="create-dns-records-at-freenom-for-microsoft"></a>Freenom で Microsoft 用の DNS レコードを作成する

Freenom の Web サイトでは、追加の SRV レコードはサポートされません。つまり、Teams とメールのいくつかの機能は動作しません。どの Microsoft プランでも、かなりのサービスの制限事項があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。

## <a name="create-dns-records-at-mydomain-for-microsoft"></a>Microsoft 用の MyDomain で DNS レコードを作成する

MyDomain の Web サイトでは、SRV レコードはサポートされません。つまり、Teams とメールのいくつかの機能は動作しません。どの Microsoft プランでも、MyDomain で DNS レコードを管理する場合は、かなりのサービスの制限事項があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。

## <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows ベースの DNS を使って Microsoft の DNS レコードを作成する

自分のドメインの DNS レコードがあるページに移動します。 Windows Server 2008 を使っている場合は、[**スタート**]、[**ファイル名を指定して実行**] の順にクリックします。 Windows Server 2012 を使っている場合は、**Windows キー** を押して、**R** キーを押します。 「**dnsmgmnt.msc**」と入力して、[**OK**] を選択します。 DNS マネージャーで、[**DNS サーバー名**]、[**前方参照ゾーン**] の順に展開します。 ドメインを選択します。 これで DNS レコードを作成する準備が整いました。

## <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Google がドメインを管理している場合に DNS レコードを作成する (eNom)

Google Apps for Work アカウントへのサインアップ中に Google 経由でドメインを購入した場合、DNS レコードは Google によって管理されますが、eNom に登録されます。Google Domains ページから eNom にアクセスし、DNS を作成できます。

## <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Microsoft 用の 1&1 IONOS fで DNS レコードを作成する

1&1 IONOS では、1 つのドメインに MX レコードとトップレベルの自動検出 CNAME レコードの両方が存在することはできません。 このため、Exchange Online for Microsoft を構成する方法が制限されます。 回避策はありますが、1&1 IONOS でサブドメインを作成した経験がある場合にのみ使うことをお勧めします。

このサービスの制限にもかかわらず 1&1 IONOS で自分の Microsoft DNS レコードを管理する場合は、この記事に示す手順に従い、ドメインを確認してメールや Skype for Business Online などの DNS レコードを設定します。

1&1 IONOS で Microsoft メール サービスに必要な CNAME レコードと共に MX レコードを使うことができるようにするには、ある対処法を実行する必要があります。 この対処法では、1&1 IONOS でサブドメインのセットを作成して CNAME レコードに割り当てる必要があります。

> [!NOTE]
> この手順を開始する前に、利用可能なサブドメインが 2 つ以上あることを確認してください。この解決策は、1&1 IONOS でサブドメインを作成した経験がある場合にのみ使うことをお勧めします。

### <a name="basic-cname-records"></a>基本的な CNAME レコード

1.  まず、1&1 IONOS でドメイン ページにアクセスします。ログインするように求められます。

1.  [**Manage domains**] を選択します。

1.  [Domain Center] ページで、更新するドメインを見つけ、[**Manage Subdomains**] を選びます。 ここで 2 つのサブドメインを作成し、それぞれに **Alias** 値を設定します (1&1 IONOS ではトップレベルの CNAME レコードは 1 つしかサポートしませんが、Microsoft では複数の CNAME レコードが必要であるため、この設定が必要です)。

1.  最初に、Autodiscover サブドメインを作成します。 [**Subdomain Overview**] セクションで、[**Create Subdomain**] を選択します。

1.  新しいサブドメインの [**Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます。 (**Alias** 値は後の手順で追加します。)

    |Create Subdomain|Alias|
    |:----|:----|
    |autodiscover|autodiscover.outlook.com|

1.  [**Create Subdomain**] を選択します。

1.  [**Subdomain Overview**] セクションで、作成した [autodiscover] サブドメインを見つけます。次に、このサブドメインの [Panel (v)] コントロールを選択します。

1.  [**Subdomain Settings**] 領域で、[**Edit DNS Settings**] を選択します。

1.  [**A/AAAA Records (IP Addresses)**] セクションの [**IP address (A Record)**] 領域で、[**CNAME**] を選びます。

1. [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。

    |Create Subdomain|Alias|
    |:----|:----|
    |autodiscover|autodiscover.outlook.com|

1. 免責事項の [ **I am aware**] チェック ボックスをオンにします。

1. **[保存]** を選択します。

### <a name="additional-cname-records"></a>追加の CNAME レコード

以降の手順で追加した CNAME レコードでは、Skype for Business Online サービスが有効になります。前に 2 つの CNAME レコードを作成したときの手順と同じ手順を使用します。

**3 つ目のサブドメイン (Lyncdiscover) を作成します**

1.  [**Subdomain Overview**] セクションで、[**Create Subdomain**] を選択します。

1.  新しいサブドメインの [**Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます。 (**Alias** 値は後の手順で追加します。)

    |Create Subdomain|Alias|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  [**Create Subdomain**] を選択します。

1.  [Domain Center] ページで、[**Manage Subdomains**] を選びます。

1.  [**Subdomain Overview**] セクションで、作成した [lyncdiscover] サブドメインを見つけます。次に、このサブドメインの [Panel (v)] コントロールを選びます。 [**Subdomain Settings**] 領域で、[**Edit DNS Settings**] を選択します。

1.  [**A/AAAA Records (IP Addresses)**] セクションの [**IP address (A Record)**] 領域で、[**CNAME**] を選びます。

1.  [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。

    |Create Subdomain|Alias|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  免責事項の [ **I am aware**] チェック ボックスをオンにして、[ **Save**] を選択します。

1.  [**Edit DNS Settings**] ダイアログ ボックスで、[**Yes**] を選択します。

**4 つ目のサブドメイン (SIP) を作成します**

1.  [**Subdomain Overview**] セクションで、[**Create Subdomain**] を選択します。

1.  新しいサブドメインの [**Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます。 (**Alias** 値は後の手順で追加します。)

    |Create Subdomain|Alias|
    |:----|:----|
    |sip|sipdir.online.lync.com|  

1.  [**Create Subdomain**] を選択します。

1.  [Domain Center] ページで、[**Manage Subdomains**] を選びます。

1.  [**Subdomain Overview**] セクションで、作成した [sip] サブドメインを見つけます。次に、このサブドメインの [Panel (v)] コントロールを選択します。 <br/> [**Subdomain Settings**] 領域で、[**Edit DNS Settings**] を選択します。

1.  [**A/AAAA Records (IP Addresses)**] セクションの [**IP address (A Record)**] 領域で、[**CNAME**] を選びます。

1.  [**Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。

    |Create Subdomain|Alias|
    |:----|:----|
    |sip|sipdir.online.lync.com|

1.  免責事項の [ **I am aware**] チェック ボックスをオンにして、[ **Save**] を選択します。

1.  [**Edit DNS Settings**] ダイアログ ボックスで、[**Yes**] を選択します。

### <a name="cname-records-needed-for-mdm"></a>MDM に必要な CNAME レコード

手順は、他の 4 つの CNAME レコードと同じですが、以下の値を入力します。

|Create Subdomain|Alias|
|:----|:----|
|enterpriseregistration|enterpriseregistration.windows.net|
|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|

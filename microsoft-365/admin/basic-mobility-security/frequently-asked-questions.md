---
title: 基本的なモビリティとセキュリティに関するよく寄せられる質問 (FAQ)
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
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
description: 基本的なモビリティとセキュリティについてよく寄せられる質問。
ms.openlocfilehash: e05815392510ad54bb530457d7f0f6490ece4a95
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430236"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>基本的なモビリティとセキュリティに関するよく寄せられる質問 (FAQ)

この記事には、Microsoft 365 でのモバイルデバイスの管理およびセキュリティ保護に役立つ機能である基本的なモビリティとセキュリティに関してよく寄せられる質問が含まれています。 質問に対する回答が見つからない場合は、この記事に質問を追加できるように、ページにコメントを残してお知らせください。

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>基本的なモビリティとセキュリティを利用するにはどうすればよいですか? Microsoft 365 管理センターに表示されない

1.  [Office 365 セキュリティ & コンプライアンス](https://protection.office.com/)ページに移動して、基本的なモビリティとセキュリティを有効にします。   

2.  [データ損失防止 > デバイス管理] に移動します。   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>基本的なモビリティとセキュリティでデバイスの管理を開始するには、どうすればよいですか。

基本的なモビリティとセキュリティの使用を開始するには、次の4つの手順を実行します。 

1. [Office 365 セキュリティ & コンプライアンス](https://protection.office.com/)に移動して、基本的なモビリティとセキュリティを有効にします。
    
2. [データ損失防止 > デバイス管理 > デバイスポリシー] に移動します。
    
3. デバイス管理ポリシーを作成し、セキュリティグループに設定されているユーザーのグループに適用します。 最初に、小規模なテストグループにポリシーを展開することをお勧めします。 詳細については、「 [Create device security policies In Basic Mobility And security](create-device-security-policies.md)」を参照してください。      

4. ポリシーが適用されているユーザーは、Microsoft 365 データにアクセスしようとすると、デバイスを登録するように求められます。 詳細については、「 [Basic Mobility And Security を使用してモバイルデバイスを登録する](enroll-your-mobile-device.md)」を参照してください。

詳細については、「 [基本モビリティとセキュリティを設定](set-up.md)する」を参照してください。

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>基本的なモビリティとセキュリティを設定しようとしていますが、まだ動かないように見えます。 Microsoft 365 Service Health は、しばらくの間「プロビジョニング」を示しています。 解決方法

サービスの準備が整うまでしばらく時間がかかる場合があります。 プロビジョニングが完了すると、Microsoft 365 のモバイルデバイス管理ページが表示されます。 24時間待機していて、状態がまだプロビジョニングされている場合は、サポートにお問い合わせください。また、問題の内容について説明します。 サポートオプションについては、「[ヘルプが必要ですか?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) 」を参照してください。 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>デバイスの登録が失敗した場合はどうすればよいですか。

登録済みデバイスの取得で問題が発生した場合は、まず次のことを確認してください。

- デバイスが Intune などの他のモバイルデバイス管理プロバイダーに登録されていないことを確認してください。
    
- デバイスが正しい日付と時刻に設定されていることを確認します。
    
- デバイス上の別の WIFI または携帯ネットワークに切り替えます。
    
- Android または iOS デバイスの場合は、デバイス上の Intune ポータルサイトアプリをアンインストールしてから再インストールします。
    
登録がまだ機能していない場合は、「 [基本的なモビリティとセキュリティのトラブルシューティング](troubleshoot.md)」を参照してください。

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune と基本的なモビリティとセキュリティの違いは何ですか。

基本的なモビリティとセキュリティは、Intune サービスによってホストされます。 これは、Microsoft 365 に追加のメリットとして提供される Intune サービスのサブセットであり、組織内のデバイスを管理するための組み込みのクラウドベースのソリューションです。 2つのサービスを並べて比較して、Microsoft 365 の Intune または基本的なモビリティとセキュリティを使用することが最適であるかどうかを判断するには、「 [基本モビリティセキュリティと Intune の選択](choose-between-basic-mobility-and-security-and-intune.md)」を参照してください。

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>基本的なモビリティとセキュリティのためのポリシーの仕組み どのように設定すればよいですか? 無効にしますか?

基本的なモビリティとセキュリティの初期セットアップを完了したら、セキュリティ & コンプライアンスセンターでポリシーを作成し、ユーザーのグループに適用します。 ポリシーのユーザーは、デバイスを使用して Microsoft 365 データにアクセスする前に、基本的なモビリティとセキュリティでデバイスを登録する必要があります。 設定したポリシーによって、モバイルデバイスの設定が決定されます。たとえば、パスワードをリセットする頻度や、データの暗号化が必要かどうかなどがあります。 詳細については、「 [Create device security policies In Basic Mobility And security](create-device-security-policies.md)   and [Microsoft 365 コンプライアンスセンター](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)」を参照してください。

デバイスポリシーを作成して展開するための詳細な手順については、「 [Create device security policies In Basic Mobility And security](create-device-security-policies.md)」を参照してください。

特定のユーザーグループがポリシーの影響を受けないようにするには、除外グループにグループを追加します。

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Exchange ActiveSync デバイス管理から Microsoft 365 の基本的なモビリティとセキュリティに切り替えることはできますか?

モバイルデバイスを管理するために Exchange ActiveSync ポリシーをすでに使用している場合は、「基本的なモビリティとセキュリティを設定する」の手順に従って、基本的なモビリティとセキュリティの使用を開始できます。 詳細については、「 [ユーザーとデバイスのアクセスを保護](https://go.microsoft.com/fwlink/?LinkId=615145) する」と「 [基本的なモビリティとセキュリティを設定](set-up.md)する」を参照してください。

基本的なモビリティとセキュリティで作成したポリシーをユーザーのグループに適用すると、これらのポリシーは exchange ActiveSync モバイルデバイスメールボックスポリシーと、それらのユーザーの Exchange 管理センターで以前に作成したデバイスアクセスルールよりも優先されます。

基本的なモビリティとセキュリティにデバイスを登録した後、デバイスに適用された Exchange ActiveSync モバイルデバイスメールボックスポリシーまたはデバイスアクセスルールは無視されます。

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>基本的なモビリティとセキュリティを設定しましたが、これを削除したいと思います。 手順について

残念ながら、セットアップ後に基本的なモビリティとセキュリティを単に "準備解除" することはできません。 ただし、作成したデバイスポリシーからユーザーのセキュリティグループを削除することによって、ユーザーのグループのために削除することができます。 または、デバイスポリシーを削除してすべてのユーザーに対して無効にし、適用されないようにすることができます。 詳細については、「 [基本的なモビリティとセキュリティをオフにする](turn-off.md)」を参照してください。


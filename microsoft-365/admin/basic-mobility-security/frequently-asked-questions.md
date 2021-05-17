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
description: Basic Mobility and Security に関するよく寄せられる質問。
ms.openlocfilehash: 14e12678ec210325f63914594fb6debcf7abb880
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023895"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>基本的なモビリティとセキュリティに関するよく寄せられる質問 (FAQ)

この記事では、モバイル デバイスの管理とセキュリティをサポートする機能である Basic Mobility and Security に関してよく寄せられる質問をMicrosoft 365。 質問に対する回答が見つからなかった場合は、ページにコメントを残して、この記事への質問の追加を検討してください。

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Basic Mobility and Security を取得する方法 管理センターに表示Microsoft 365しない

1.  [基本モビリティとセキュリティ] をアクティブにするには、[セキュリティとコンプライアンス] Office 365[ページ&移動](https://protection.office.com/)します。

2.  [デバイス管理] の [データ損失>に移動します。

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Basic Mobility and Security でデバイス管理を開始するには、どうすれば良いですか?

Basic Mobility and Security の使用を開始するには、次の 4 つの手順を実行します。 

1. [基本モビリティとセキュリティ] をアクティブにするには、[セキュリティ] Office 365[コンプライアンス&します](https://protection.office.com/)。

2. [デバイス ポリシー] の [データ損失>管理>に移動します。
    
3. デバイス管理ポリシーを作成し、セキュリティ グループで設定されているユーザーのグループに適用します。 まず、ポリシーを小規模なテスト グループに展開することをお勧めします。 詳細については、「Basic [Mobility and Security でデバイス セキュリティ ポリシーを作成する」を参照してください](create-device-security-policies.md)。

4. ポリシーが適用されているユーザーは、ユーザーがデータにアクセスしようとするときに、デバイスの登録を求Microsoft 365されます。 詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。

詳細については [、「Set up Basic Mobility and Security 」を参照してください](set-up.md)。

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>基本的なモビリティとセキュリティをセットアップしていますが、スタックしているようです。 サービスMicrosoft 365はしばらくの間"プロビジョニング" を表示しています。 解決方法

サービスの準備に時間がかかる場合があります。 プロビジョニングが完了すると、[基本モビリティとセキュリティ] ページが表示されます。 24 時間待機し、状態がまだプロビジョニングされている場合は、サポートに問い合わせ、問題の把握に役立ちます。

## <a name="what-can-i-do-if-device-enrollment-fails"></a>デバイスの登録に失敗した場合はどうなりますか?

デバイスの登録に問題がある場合は、まず次の情報を確認してください。

- デバイスが Intune などの別のモバイル デバイス管理プロバイダーに既に登録されていないか確認します。

- デバイスが正しい日付と時刻に設定されていることを確認します。

- デバイス上の別の WIFI または携帯電話ネットワークに切り替えます。

- Android デバイスまたは iOS デバイスの場合は、デバイス上の Intune ポータル サイトアプリをアンインストールして再インストールします。
    
登録がまだ機能しない場合は、「基本モビリティとセキュリティの [トラブルシューティング」を参照してください](troubleshoot.md)。

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune と Basic Mobility and Security の違いは何ですか?

基本的なモビリティとセキュリティは Intune サービスによってホストされます。 これは、Microsoft 365 の追加の利点として提供される Intune サービスのサブセットであり、組織内のデバイスを管理するための組み込みのクラウドベースのソリューションです。 Intune または Basic Mobility and Security for Microsoft 365 を使用する場合に最適な 2 つのサービスのサイド バイ サイド比較については、「Choose between Basic Mobility Security and [Intune」](choose-between-basic-mobility-and-security-and-intune.md)を参照してください。

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Basic Mobility and Security のポリシーの動作 それらを設定する方法 無効にしますか?

Basic Mobility and Security の初期セットアップが完了したら、ポリシーを作成し、ポリシーをセキュリティ コンプライアンス センターのユーザー グループ&適用します。 ポリシーでは、ポリシーのユーザーがデバイスを Basic Mobility and Security に登録する必要があります。その後、デバイスを使用してデータにアクセスMicrosoft 365があります。 設定するポリシーによって、モバイル デバイスの設定 (パスワードをリセットする頻度、データ暗号化が必要かどうかなど) が決められます。 詳細については、「Create [device security policies](create-device-security-policies.md)in Basic Mobility and Security and Microsoft 365   コンプライアンス センター」[を参照してください](../../compliance/microsoft-365-compliance-center.md)。

デバイス ポリシーの作成と展開の手順については、「Create device security policies in Basic Mobility and [Security」を参照してください](create-device-security-policies.md)。

特定のグループのユーザーをポリシーの影響を受けから除外する場合は、除外グループにグループを追加できます。

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>デバイス管理から基本モビリティExchange ActiveSyncセキュリティに切り替Microsoft 365?

モバイル デバイスの管理に Exchange ActiveSyncポリシーを既に使用している場合は、基本モビリティとセキュリティをセットアップする手順に従って、Basic Mobility and Security の使用を開始できます。 詳細については、「ユーザーとデバイスの [アクセスを保護](../../compliance/protect-access-to-data-and-services.md) する」および「 [基本モビリティとセキュリティのセットアップ」を参照してください](set-up.md)。

Basic Mobility and Security で作成したポリシーをユーザーのグループに適用すると、これらのポリシーは、それらのユーザーの Exchange 管理センターで以前に作成した Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。

デバイスが Basic Mobility and Security に登録されると、Exchange ActiveSyncに適用されるモバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールが無視されます。

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Basic Mobility and Security をセットアップしましたが、削除する必要があります。 手順は何ですか?

残念ながら、基本モビリティとセキュリティをセットアップした後は、単に "プロビジョニング解除" を行う必要があります。 ただし、作成したデバイス ポリシーからユーザー セキュリティ グループを削除することで、ユーザーのグループに対して削除できます。 または、デバイス ポリシーを削除して、デバイス ポリシーが設定されておらず、強制されないので、すべてのユーザーに対して無効にすることもできます。 詳細については、「基本モビリティと [セキュリティをオフにする」を参照してください](turn-off.md)。
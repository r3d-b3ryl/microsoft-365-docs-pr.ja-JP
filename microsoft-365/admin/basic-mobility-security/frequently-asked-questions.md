---
title: モビリティとセキュリティに関する基本的なよく寄せられる質問 (FAQ)
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
description: Basic Mobility and Security についてよく寄せられる質問です。
ms.openlocfilehash: 5651b9f9742c45f1229e55b298cf78532c835c9a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876878"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>モビリティとセキュリティに関する基本的なよく寄せられる質問 (FAQ)

この記事では、Microsoft 365 のモバイル デバイスの管理とセキュリティ保護に役立つ機能である Basic Mobility and Security についてよく寄せられる質問について説明します。 質問に対する回答が見当たらない場合は、この記事に質問を追加する方法を検討できるよう、ページにコメントを残してお知らせします。

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Basic Mobility and Security を取得する方法 Microsoft 365 管理センターに表示しない

1.  [Basic Mobility and Security] をアクティブにするには、[Office [365 Security & Compliance] ページに移動](https://protection.office.com/) します。

2.  デバイス管理のデータ損失防止>に移動します。

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Basic Mobility and Security でデバイス管理を開始する方法

Basic Mobility and Security の使用を開始するには、次の 4 つの手順があります。 

1. Office 365 Security & Compliance に移動して、Basic [Mobility and Security をアクティブ化します](https://protection.office.com/)。

2. [デバイスの管理] ポリシー>データ損失>に移動します。
    
3. デバイス管理ポリシーを作成し、セキュリティ グループで設定されているユーザーのグループに適用します。 最初に、ポリシーを小規模なテスト グループに展開することをお勧めします。 詳しくは、「Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成 [」をご覧ください](create-device-security-policies.md)。

4. ポリシーが適用されているユーザーは、Microsoft 365 データにアクセスしようとするときにデバイスの登録を求めるメッセージが表示されます。 詳細については [、「Basic Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。

詳細については [、「Basic Mobility and Security のセットアップ」を参照してください](set-up.md)。

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Basic Mobility and Security をセットアップしていますが、行き詰まっているようです。 Microsoft 365 Service Health はしばらくの間、"プロビジョニング" を表示しています。 解決方法

サービスの準備に時間がかかる場合があります。 プロビジョニングが完了すると、[Basic Mobility and Security] ページが表示されます。 24 時間待機し、状態がまだプロビジョニング中の場合は、サポートにお問い合わせください。問題の把握については、サポートにお問い合わせください。 サポート オプションについては、「サポート [が必要な場合」を参照してください](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp)。

## <a name="what-can-i-do-if-device-enrollment-fails"></a>デバイスの登録が失敗した場合の処理

デバイスの登録で問題が発生した場合は、まず次のチェックを行います。

- デバイスが Intune などの別のモバイル デバイス管理プロバイダーに登録されていないか確認します。

- デバイスが正しい日付と時刻に設定されていることを確認します。

- デバイス上の別の WIFI または携帯ネットワークに切り替えます。

- Android または iOS デバイスの場合は、Intune ポータル サイト アプリをアンインストールし、デバイスに再インストールします。
    
登録がまだ機能しない場合は、「Basic Mobility and Security のトラブルシューティング [」を参照してください](troubleshoot.md)。

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune と Basic Mobility and Security の違いは何ですか?

Basic Mobility and Security は Intune サービスによってホストされます。 これは、Microsoft 365 の追加の利点として提供される Intune サービスのサブセットであり、組織内のデバイスを管理するための組み込みのクラウドベースのソリューションです。 Intune を使用するか、Microsoft 365 の Basic Mobility and Security を使用するかの判断に役立つ 2 つのサービスの比較が最適な場合は [、「Basic Mobility Security](choose-between-basic-mobility-and-security-and-intune.md)と Intune の選択」を参照してください。

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Basic Mobility and Security のポリシーの動作 セットアップ方法 無効にしますか?

Basic Mobility and Security の初期セットアップが完了したら、ポリシーを作成し、セキュリティ/コンプライアンス センターのユーザー グループ&適用します。 ポリシーでは、デバイスを使用して Microsoft 365 データにアクセスする前に、ポリシーのユーザーがデバイスを Basic Mobility and Security に登録する必要があります。 設定したポリシーによって、モバイル デバイスの設定が決められます。たとえば、パスワードをリセットする頻度や、データの暗号化が必要かどうかなどです。 詳細については[、「Basic Mobility and Security](create-device-security-policies.md)および Microsoft 365 コンプライアンス センターでのデバイス セキュリティ ポリシー   [の作成」を参照してください](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)。

デバイス ポリシーを作成および展開する詳しい手順については [、「Basic Mobility and Security」](create-device-security-policies.md)の「デバイス セキュリティ ポリシーの作成」を参照してください。

特定のユーザー グループがポリシーの影響を受けから除外する場合は、除外グループにグループを追加できます。

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>デバイス管理から Microsoft 365 Exchange ActiveSync Basic Mobility and Security に切り替えできますか?

モバイル デバイスの管理に Exchange ActiveSync ポリシーを既に使用している場合は、Basic Mobility and Security をセットアップする手順に従って Basic Mobility and Security の使用を開始できます。 詳細については、「ユーザーとデバイスの [アクセスを保護](https://go.microsoft.com/fwlink/?LinkId=615145) する」および [「Basic Mobility and Security をセットアップする」を参照してください](set-up.md)。

Basic Mobility and Security で作成したポリシーをユーザー グループに適用すると、これらのポリシーは、それらのユーザーの Exchange 管理センターで以前に作成した Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールより優先されます。

デバイスを Basic Mobility and Security に登録すると、そのデバイスに適用Exchange ActiveSyncモバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Basic Mobility and Security をセットアップしましたが、削除します。 手順は何ですか?

残念ながら、Basic Mobility and Security をセットアップした後は、単に"準備を解除" する必要があります。 ただし、作成したデバイス ポリシーからユーザー セキュリティ グループを削除することで、ユーザーのグループに対して削除できます。 または、デバイス ポリシーが適用されておらず、適用されないデバイス ポリシーを削除することで、すべてのユーザーに対して無効にすることもできます。 詳細については [、「Basic Mobility and Security をオフにする」を参照してください](turn-off.md)。
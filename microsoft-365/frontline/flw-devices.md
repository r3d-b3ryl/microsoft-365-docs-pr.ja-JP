---
title: 現場担当者向けのモバイル デバイスを管理する
author: lanachin
ms.author: v-lanachin
ms.reviewer: mabolan
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
ms.localizationpriority: high
search.appverid: MET150
description: 組織内の現場担当者向けのモバイル デバイスの管理の概要について説明します。
ms.collection: m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: e0da7bf29865520507d9355fe25115700c3d8e28
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994644"
---
# <a name="manage-mobile-devices-for-frontline-workers"></a>現場担当者向けのモバイル デバイスを管理する

## <a name="overview"></a>概要

すべての業界において、現場担当者が従業員の大きな割合を占めています。 現場担当者の役割には、小売担当者、工場勤務者、現場およびサービス技術者、医療従事者などが含まれます。

多くの従業員は移動性が高く、多くの場合シフトベースであるため、現場担当者が使用するデバイスを管理することが重要な基本です。 考慮すべきいくつかのポイント:

- 従業員は会社所有のデバイスを使用しますか？ または個人のデバイスを使用しますか?
- 会社所有のデバイスは、従業員間で共有されていますか? または個人に割り当てられていますか?
- 従業員はデバイスを自宅に持ち帰りますか? または職場に置きますか?

セキュリティで保護された準拠ベースラインを設定して、共有デバイスでも従業員自身のデバイスでも、従業員のデバイスを管理することが重要です。 この記事では、一般的な現場の従業員デバイスのシナリオと管理機能の概要を説明し、会社のデータを保護しながら従業員をエンパワーできます。

## <a name="my-staff"></a>マイ スタッフ

Azure Active Directory (Azure AD) の [マイ スタッフ](/azure/active-directory/roles/my-staff-configure) 機能を使用すると、マイ スタッフ ポータルを使用して、一般的なユーザー管理タスクを現場マネージャーに委任できます。 現場マネージャーは、ヘルプデスク、オペレーション、または IT に要求をルーティングすることなく、直接ストアまたは工場のフロアから、現場担当者のパスワードをリセットしたり、電話番号を管理したりできます。

また、現場マネージャーは、チーム メンバーの電話番号を SMS サインインに登録することもできます。 組織内で [SMS ベースの認証](/azure/active-directory/authentication/howto-authentication-sms-signin) が有効になっている場合、現場担当者は電話番号と SMS 経由で送信されたワンタイム パスコードのみを使用して Teams やその他のアプリにサインインできます。 これにより、現場担当者のサインインが簡単かつ安全で、高速になります。

## <a name="shared-devices"></a>共有デバイス

多くの現場担当者は、共有のモバイル デバイスを使用して作業を行います。 共有デバイスは、会社所有のデバイスであり、タスク、シフト、または場所をまたいで従業員間で共有されます。

ここでは、一般的なシナリオの例を紹介します。 組織には、充電クレードルにすべての従業員間で共有されるデバイスのプールがあります。 シフトの開始時に、従業員はプールからデバイスを取り出し、自分の役割に不可欠な Teams やその他のビジネス アプリにサインインします。 シフトの終了時に、サインアウトしてデバイスをプールに返します。 同じシフト内でも、従業員は、タスクが完了したときにデバイスを返すや、昼食のために退勤してから、別のデバイスを取り出す場合があります。

共有デバイスには、ユニークなセキュリティ上の課題があります。 たとえば、従業員は、同じデバイス上の他のユーザーが利用すべきでない会社または顧客のデータにアクセスできる場合があります。

このセクションでは、現場担当者の共有デバイスを管理するために使用できる機能の概要について説明します。

### <a name="shared-device-mode"></a>共有デバイス モード

[共有デバイス モード](/azure/active-directory/develop/msal-shared-devices) は、従業員が共有するようにデバイスを構成できる Azure AD の機能です。 この機能を使用すると、Microsoft Teams および共有デバイス モードをサポートしているその他のすべてのアプリに対して、シングル サインオン (SSO) とデバイス全体のサインアウトが可能になります。 この機能は、Microsoft Authentication Library (MSAL) を使用して基幹業務 (LOB) アプリに統合できます。

Teams を例として、共有デバイス モードのしくみを説明します。 従業員がシフトの開始時に Teams にサインインすると、デバイスで共有デバイス モードをサポートしている他のすべてのアプリに自動的にサインインされます。 シフトが終了した際、Teams からサインアウトすると、共有デバイス モードをサポートしている他のすべてのアプリからグローバルにサインアウトされます。 サインアウト後、Teams 内の従業員のデータと会社のデータ (中でホストされているアプリを含む)、および共有デバイス モードをサポートする他のすべてのアプリにアクセスできなくなります。 デバイスは準備完了で、次の従業員へ安全に受け渡すことができます。

Microsoft エンドポイント マネージャーの Microsoft Intuneなどのモバイル デバイス管理 (MDM) ソリューションを使用して、[Microsoft Authenticator アプリ](https://support.microsoft.com/account-billing/how-to-use-the-microsoft-authenticator-app-9783c865-0308-42fb-a519-8cf666fe0acc) をインストールして共有モードをオンにすることで、共有するデバイスを準備します。 共有デバイス モードをサポートする Teams およびその他のすべてのアプリでは、共有モードの設定を使用してデバイス上のユーザーを管理します。 使用する MDM ソリューションは、サインアウトが発生したときにデバイスのクリーンアップを実行する必要もあります。

現在、共有デバイス モードは Android デバイスでサポートされています。 以下のリソースも、利用を開始するときに役立ちます。

#### <a name="enroll-android-devices-into-shared-device-mode"></a>Android デバイスを共有デバイス モードに登録する

Intune を使用して Android デバイスを共有デバイス モードに管理および登録するには、デバイスが Android OS バージョン 8.0 以降を実行しており、Google Mobile Services (GMS) への接続が必要です。 詳細については、次を参照してください。

- [Android Enterprise 専用デバイスの Intune 登録を設定する](/mem/intune/enrollment/android-kiosk-enroll)
- [Android Enterprise 専用デバイスを共有デバイス モードAzure AD に登録する](https://techcommunity.microsoft.com/t5/intune-customer-success/enroll-android-enterprise-dedicated-devices-into-azure-ad-shared/ba-p/1820093)

Microsoft Managed Home Screen アプリを展開して、Intune に登録された Android 専用デバイスでユーザーのエクスペリエンスを調整することもできます。 マネージド ホーム画面は、他の承認済みアプリをその上で実行するための起動ツールとして機能し、デバイスをカスタマイズし、従業員がアクセスできる機能を制限することができます。 たとえば、ホーム画面でのアプリの表示方法を定義したり、会社のロゴを追加したり、カスタム壁紙を設定したり、従業員がセッション PIN を設定できるようにしたりできます。 指定した一定期間の非アクティブの期間後に自動的にサインアウトするように構成することもできます。  詳細については、次を参照してください。

- [「Android Enterprise 用の Microsoft Managed Home Screen アプリを構成する」](/mem/intune/apps/app-configuration-managed-home-screen-app)
- [マルチアプリ キオスク モードで専用デバイスに Microsoft マネージド ホーム画面を設定する方法](https://techcommunity.microsoft.com/t5/intune-customer-success/how-to-setup-microsoft-managed-home-screen-on-dedicated-devices/ba-p/1388060)

#### <a name="for-developers-creating-apps-for-shared-device-mode"></a>共有デバイス モード用のアプリを作成する開発者向け

開発者の場合は、アプリを共有デバイス モードと統合する方法の詳細については、次のリソースを参照してください:

- [Android デバイスの共有デバイス モード](/azure/active-directory/develop/msal-android-shared-devices)
- [iOS デバイスの共有デバイス モード](/azure/active-directory/develop/msal-ios-shared-devices)

## <a name="personal-devices-byod"></a>個人用デバイス (BYOD)

一部の組織では、現場担当者が個人用のモバイル デバイスを使用して Teams やその他のビジネス アプリにアクセスする、個人所有デバイスの持ち込み (BYOD) モデルを使用しています。 個人用デバイスのアクセスとコンプライアンスを管理するいくつかの方法の概要を説明します。

### <a name="enroll-android-and-ios-personal-devices"></a>個人用の Android と iOS デバイスを登録する

会社所有のデバイスに加えて、ユーザー個人所有のデバイスをIntune 管理に[登録](/mem/intune/enrollment/device-enrollment)できます。 BYOD 登録するには、Microsoft エンドポイント マネージャー管理センターにデバイス ユーザーを追加し、登録エクスペリエンスを構成し、Intune ポリシーを設定します。 ユーザーは、デバイスにインストールされている Intune ポータル サイト アプリで自分で登録を完了します。

場合によっては、ユーザーは個人のデバイスを管理に登録することに消極的な場合があります。 デバイス登録がオプションでない場合は、モバイル アプリケーション管理 (MAM) アプローチを選択し、 [アプリ保護ポリシー](/mem/intune/apps/app-protection-policies) を使用して、企業データを含むアプリを管理できます。 たとえば、Teams および Office モバイル アプリにアプリ保護ポリシーを適用して、会社のデータがデバイス上の個人用アプリにコピーされないようにすることができます。

詳細については、「[個人のデバイスと組織所有のデバイス](/mem/intune/fundamentals/intune-planning-guide#personal-devices-vs-organization-owned-devices)」と「[展開ガイダンス: Microsoft Intune でデバイスを登録する](/mem/intune/fundamentals/deployment-guide-enrollment)」を参照してください。

### <a name="off-shift-access-controls-in-teams"></a>Teams のオフシフト アクセス制御

オフシフト アクセス制御は、従業員がシフト外の場合に Teams へのアクセスを制限するのに役立ちます。 この機能を使用すると、従業員が勤務時間外にアプリにアクセスしたときにメッセージを表示するように Teams を設定できます。 現場担当者は、メッセージを確認し同意してから、Teams を使用する必要があります。

既定のメッセージは、勤務時間外に Teams を使用する時間に対して支払われないことを従業員に通知します。 既定のメッセージを使用したり、定義済みのメッセージを選択したり、独自のメッセージを表示したりできます。 この機能は、従業員がシフトでないときに思わず働かないようにするのに役立ち、労働規制に準拠するのに役立ちます。

詳細については、「[Teams へのオフシフト アクセス](manage-shift-based-access-flw.md#off-shift-access-to-teams)」を参照してください。

## <a name="related-articles"></a>関連記事

- [現場担当者管理](/azure/active-directory/fundamentals/frontline-worker-management)

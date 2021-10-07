---
title: 基本モビリティとセキュリティの概要 (Microsoft 365
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
description: 基本モビリティとセキュリティを使用して、デバイス のセキュリティ ポリシーとアクセス ルールを設定します。
ms.openlocfilehash: 4fb1b8ca467d86259f2608af5140510a2a88b23a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166002"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>基本モビリティとセキュリティの概要 (Microsoft 365

モバイル デバイスが組織に接続されている場合は、Basic Mobility and Security をMicrosoft 365して、モバイル デバイスを管理および保護できます。 スマートフォンやタブレットなどのモバイル デバイスを使用して仕事の電子メール、予定表、連絡先、ドキュメントにアクセスすることは、社員が自分たちの仕事をいつでも、どこからでも確実に行ううえで大きな役割を果たします。 そのため、ユーザーがデバイスを使用するときに組織の情報を保護する際に役立つ必要があります。 Basic Mobility and Security を使用すると、デバイスのセキュリティ ポリシーとアクセス ルールを設定したり、モバイル デバイスが紛失したり盗まれたりした場合にモバイル デバイスをワイプできます。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本的なモビリティとセキュリティのセットアップ。":::

## <a name="what-types-of-devices-can-you-manage"></a>管理できるデバイスの種類

Basic Mobility and Security を使用すると、さまざまな種類のモバイル デバイス (Windows Phone、Android、iPhone、iPad。 組織内のユーザーが使用するモバイル デバイスを管理するには、各ユーザーが該当する Microsoft 365 ライセンスを持っている必要があります。デバイスは Basic Mobility and Security に登録する必要があります。

デバイスの種類ごとにサポートされる基本モビリティとセキュリティについては、「基本モビリティとセキュリティの機能」 [を参照してください](capabilities.md)。

## <a name="setup-steps-for-basic-mobility-and-security"></a>基本モビリティとセキュリティのセットアップ手順

グローバルMicrosoft 365管理者は、Basic Mobility and Security をアクティブ化してセットアップするには、次の手順を実行する必要があります。 詳細な手順については、「基本モビリティとセキュリティのセットアップ [」のガイダンスに従います](set-up.md)。 

手順の概要は次のとおりです。

**手順 1:** 基本モビリティとセキュリティのセットアップの手順に従って、基本モビリティとセキュリティ  [をアクティブ化します](set-up.md)。

**手順 2:** たとえば、IOS デバイスを管理するための ADN 証明書を作成し、ドメインのドメイン ネーム システム (DNS Windows) レコードを追加して電話をサポートするなどして、基本モビリティとセキュリティを設定します。

**手順 3:** デバイス ポリシーを作成し、ユーザーのグループに適用します。 この操作を行う場合、ユーザーは自分のデバイスで登録メッセージを受け取り、登録が完了すると、デバイスは設定したポリシーによって制限されます。 詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティポリシーとモビリティ ポリシー設定。":::

## <a name="device-management-tasks"></a>デバイス管理タスク

Basic Mobility and Security がセットアップされ、ユーザーがデバイスを登録した後、必要に応じてデバイスの管理、アクセスのブロック、デバイスのワイプを行えます。 タスクを実行する場所など、一般的なデバイス管理タスクの詳細については、「モバイル デバイス管理に登録されているデバイスを管理する」を参照[Microsoft 365。](manage-enrolled-devices.md)

## <a name="other-ways-to-manage-devices-and-apps"></a>デバイスとアプリを管理するその他の方法

モバイル アプリ管理 (MAM) が必要な場合(おそらく、ユーザーが自分のデバイスで作業プロジェクトを更新する場合)、Intune にはデバイスの登録と管理以外に別のオプションがあります。 Intune サブスクリプションを使用すると、ユーザーのデバイスが Intune に登録されていない場合でも、Azure ポータルを使用して MAM ポリシーを設定できます。 詳細については、「アプリ保護 [ポリシーの概要」を参照してください](/mem/intune/apps/app-protection-policy)。

## <a name="related-content"></a>関連コンテンツ

[基本モビリティとセキュリティのセットアップ](set-up.md) (記事)\
[基本モビリティとセキュリティを使用してモバイル デバイスを登録](enroll-your-mobile-device.md) する (記事)\
[モバイル デバイス管理に登録されているデバイスを管理する](manage-enrolled-devices.md)(Microsoft 365)\
[Basic Mobility and Security が管理するデバイスの詳細を取得](get-details-about-managed-devices.md) する (記事)
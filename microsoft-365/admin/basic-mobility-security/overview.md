---
title: Microsoft 365 の基本モビリティとセキュリティの概要
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
description: 基本モビリティとセキュリティを使用して、デバイス のセキュリティ ポリシーとアクセス ルールを設定します。
ms.openlocfilehash: e74a5df6d10f8f3fb7b420e428380af97ba75597
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906254"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365 の基本モビリティとセキュリティの概要

モバイル デバイスが Microsoft 365 組織に接続されている場合は、Basic Mobility and Security を使用して管理およびセキュリティ保護できます。 スマートフォンやタブレットなどのモバイル デバイスを使用して仕事の電子メール、予定表、連絡先、ドキュメントにアクセスすることは、社員が自分たちの仕事をいつでも、どこからでも確実に行ううえで大きな役割を果たします。 そのため、ユーザーがデバイスを使用するときに組織の情報を保護する際に役立つ必要があります。 Basic Mobility and Security を使用すると、デバイスのセキュリティ ポリシーとアクセス ルールを設定したり、モバイル デバイスが紛失したり盗まれたりした場合にモバイル デバイスをワイプできます。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本的なモビリティとセキュリティのセットアップ":::

## <a name="what-types-of-devices-can-you-manage"></a>管理できるデバイスの種類

Basic Mobility and Security を使用すると、Windows Phone、Android、iPhone、iPad など、さまざまな種類のモバイル デバイスを管理できます。 組織内のユーザーが使用するモバイル デバイスを管理するには、各ユーザーが該当する Microsoft 365 ライセンスを持っている必要があります。デバイスは Basic Mobility and Security に登録する必要があります。

デバイスの種類ごとにサポートされる基本モビリティとセキュリティについては、「基本モビリティとセキュリティの機能」 [を参照してください](capabilities.md)。

## <a name="setup-steps-for-basic-mobility-and-security"></a>基本モビリティとセキュリティのセットアップ手順

Microsoft 365 グローバル管理者は、Basic Mobility and Security をアクティブ化してセットアップするには、次の手順を実行する必要があります。 詳細な手順については、「基本モビリティとセキュリティのセットアップ [」のガイダンスに従います](set-up.md)。 

手順の概要は次のとおりです。

**手順 1:** 基本モビリティとセキュリティのセットアップの手順に従って、基本モビリティとセキュリティ  [をアクティブ化します](set-up.md)。

**手順 2:** たとえば、IOS デバイスを管理するための ADN 証明書を作成し、Windows 電話をサポートするためにドメインのドメイン ネーム システム (DNS) レコードを追加することで、Basic Mobility and Security を設定します。

**手順 3:** デバイス ポリシーを作成し、ユーザーのグループに適用します。 この操作を行う場合、ユーザーは自分のデバイスで登録メッセージを受け取り、登録が完了すると、デバイスは設定したポリシーによって制限されます。 詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティポリシーとモビリティ ポリシー設定":::

## <a name="device-management-tasks"></a>デバイス管理タスク

Basic Mobility and Security がセットアップされ、ユーザーがデバイスを登録した後、必要に応じてデバイスの管理、アクセスのブロック、デバイスのワイプを行えます。 タスクを実行する場所など、一般的なデバイス管理タスクの詳細については [、「Microsoft 365](manage-enrolled-devices.md)のモバイル デバイス管理に登録されているデバイスの管理」を参照してください。

## <a name="other-ways-to-manage-devices-and-apps"></a>デバイスとアプリを管理するその他の方法

モバイル アプリ管理 (MAM) が必要な場合(おそらく、ユーザーが自分のデバイスで作業プロジェクトを更新する場合)、Intune にはデバイスの登録と管理以外に別のオプションがあります。 Intune サブスクリプションを使用すると、ユーザーのデバイスが Intune に登録されていない場合でも、Azure ポータルを使用して MAM ポリシーを設定できます。 詳細については、「アプリ保護 [ポリシーの概要」を参照してください](/mem/intune/apps/app-protection-policy)。

## <a name="related-topics"></a>関連項目

[基本的なモビリティとセキュリティの設定](set-up.md)

[基本モビリティとセキュリティを使用してモバイル デバイスを登録する](enroll-your-mobile-device.md)

[Microsoft 365 のモバイル デバイス管理に登録されているデバイスを管理する](manage-enrolled-devices.md)

[Basic Mobility and Security が管理するデバイスの詳細を取得する](get-details-about-managed-devices.md)
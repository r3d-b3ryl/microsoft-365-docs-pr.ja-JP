---
title: Microsoft 365 の基本的なモビリティとセキュリティの概要
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
description: Basic Mobility and Security を設定して使用することで、Microsoft 365 組織に接続されているモバイル デバイスを管理し、セキュリティで保護します。
ms.openlocfilehash: b49b02b37df615aafb87b2fc520737d4ad16d515
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084501"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365 の基本的なモビリティとセキュリティの概要

モバイル デバイスが Microsoft 365 組織に接続されている場合は、基本的なモビリティとセキュリティを使用して管理し、セキュリティで保護できます。 職場のメール、予定表、連絡先、ドキュメントにアクセスするために使用されるスマートフォンやタブレットなどのモバイル デバイスは、従業員がどこからでもいつでも仕事を終わらせる上で重要な役割を果たします。 そのため、ユーザーがデバイスを使用するときに組織の情報を保護することが重要です。 Basic Mobility と Security を使用して、デバイスのセキュリティ ポリシーとアクセス規則を設定し、モバイル デバイスが紛失または盗難にあった場合はワイプすることができます。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本的なモビリティとセキュリティのセットアップ。":::

## <a name="what-types-of-devices-can-you-manage"></a>管理できるデバイスの種類

Basic Mobility and Security を使用すると、Android、iPhone、iPad などのさまざまな種類のモバイル デバイスを管理できます。 組織内のユーザーが使用するモバイル デバイスを管理するには、各ユーザーに適用可能な Microsoft 365 ライセンスが必要であり、そのデバイスは Basic Mobility and Security に登録されている必要があります。

デバイスの種類ごとに Basic Mobility と Security がサポートする内容については、「 [基本的なモビリティとセキュリティの機能」を](capabilities.md)参照してください。

## <a name="setup-steps-for-basic-mobility-and-security"></a>Basic Mobility and Security のセットアップ手順

Microsoft 365 グローバル管理者は、基本的なモビリティとセキュリティをアクティブ化して設定するには、次の手順を完了する必要があります。 詳細な手順については、「 [基本的なモビリティとセキュリティのセットアップ」](set-up.md)のガイダンスに従ってください。 

手順の概要は次のとおりです。

**手順 1:** 基本的なモビリティとセキュリティの設定の手順に従って [、基本的なモビリティとセキュリティを](set-up.md)アクティブ化します。

**手順 2:** たとえば、iOS デバイスを管理する APN 証明書を作成し、ドメインのドメイン ネーム システム (DNS) レコードを追加するなどして、基本的なモビリティとセキュリティを設定します。

**手順 3:** デバイス ポリシーを作成し、ユーザーのグループに適用します。 これを行うと、ユーザーはデバイスに登録メッセージを受け取り、登録が完了すると、デバイスは設定したポリシーによって制限されます。 詳細については、「 [Basic Mobility and Security を使用してモバイル デバイスを登録する」](enroll-your-mobile-device.md)を参照してください。 

:::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="基本的なセキュリティとモビリティのポリシー設定。":::

## <a name="device-management-tasks"></a>デバイス管理タスク

Basic Mobility and Security を設定し、ユーザーがデバイスを登録したら、必要に応じてデバイスの管理、アクセスのブロック、デバイスのワイプを行うことができます。 タスクを完了する場所など、一般的なデバイス管理タスクの詳細については、「[モバイル デバイス管理 for Microsoft 365 に登録されているデバイスの管理」を](manage-enrolled-devices.md)参照してください。

## <a name="other-ways-to-manage-devices-and-apps"></a>デバイスとアプリを管理するその他の方法

モバイル アプリ管理 (MAM) が必要な場合は、おそらく自分のデバイスで作業プロジェクトを更新するユーザーに対して、デバイスの登録と管理以外に別のオプションIntune用意されています。 Intune サブスクリプションを使用すると、ユーザーのデバイスがIntuneに登録されていない場合でも、Azure portalを使用して MAM ポリシーを設定できます。 詳細については、「[アプリ保護 ポリシーの概要](/mem/intune/apps/app-protection-policy)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[基本的なモビリティとセキュリティの設定](set-up.md) (記事)\
[Basic Mobility and Security を使用してモバイル デバイスを登録](enroll-your-mobile-device.md) する (記事)\
[モバイル デバイス管理 for Microsoft 365 に登録されているデバイスを管理する](manage-enrolled-devices.md) (記事)\
[Basic Mobility and Security によって管理されているデバイスの詳細を取得](get-details-about-managed-devices.md) する (記事)

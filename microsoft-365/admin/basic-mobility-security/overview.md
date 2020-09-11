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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティを使用して、デバイスのセキュリティポリシーとアクセスルールを設定します。
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430225"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365 の基本的なモビリティとセキュリティの概要

基本的なモビリティとセキュリティを使用して、Microsoft 365 組織に接続されているモバイルデバイスの管理とセキュリティ保護を行うことができます。 スマートフォンやタブレットなどのモバイル デバイスを使用して仕事の電子メール、予定表、連絡先、ドキュメントにアクセスすることは、社員が自分たちの仕事をいつでも、どこからでも確実に行ううえで大きな役割を果たします。 そのため、ユーザーがデバイスを使用するときに、組織の情報を保護することが重要です。 基本的なモビリティとセキュリティを使用して、デバイスのセキュリティポリシーとアクセスルールを設定したり、紛失または盗難にあったモバイルデバイスをワイプしたりできます。

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本的なモビリティとセキュリティの設定":::

## <a name="what-types-of-devices-can-you-manage"></a>管理できるデバイスの種類

基本的なモビリティとセキュリティを使用して、Windows Phone、Android、iPhone、iPad などのさまざまな種類のモバイルデバイスを管理できます。 組織内のユーザーによって使用されるモバイルデバイスを管理するには、各ユーザーに、適用可能な Microsoft 365 ライセンスが必要であり、基本的なモビリティとセキュリティにデバイスが登録されている必要があります。

基本的なモビリティとセキュリティがどの種類のデバイスに対してサポートされているかを確認するには、「 [基本的なモビリティとセキュリティの機能](capabilities.md)」を参照してください。

## <a name="setup-steps-for-basic-mobility-and-security"></a>基本的なモビリティとセキュリティのセットアップ手順

Microsoft 365 のグローバル管理者は、次の手順を実行して、基本的なモビリティとセキュリティをアクティブ化してセットアップする必要があります。 詳細な手順については、「 [Set Up Basic Mobility And Security](set-up.md)」のガイダンスに従ってください。 

手順の概要は次のとおりです。

**手順 1:** 「 [基本的なモビリティとセキュリティを設定](set-up.md)する」の手順に従って、基本的なモビリティとセキュリティをアクティブにします。

**手順 2:** IOS デバイスを管理するための APNs 証明書の作成、Windows phone をサポートするためのドメインのドメインネームシステム (DNS) レコードの追加など、基本的なモビリティとセキュリティを設定します。

**手順 3:** デバイスポリシーを作成し、ユーザーのグループに適用します。 この操作を行うと、ユーザーは自分のデバイスで登録メッセージを受け取り、登録が完了すると、それらのデバイスは設定したポリシーによって制限されます。 詳細については、「 [Basic Mobility And Security を使用してモバイルデバイスを登録する](enroll-your-mobile-device.md)」を参照してください。 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なセキュリティとモビリティのポリシー設定":::

## <a name="device-management-tasks"></a>デバイス管理タスク

基本的なモビリティとセキュリティを設定して、ユーザーがデバイスを登録した後、必要に応じて、デバイスの管理、アクセスのブロック、またはデバイスのワイプを行うことができます。 一般的なデバイス管理タスクの詳細については、「 [Microsoft 365 のモバイルデバイス管理に登録](manage-enrolled-devices.md)されているデバイスの管理」を参照してください。

## <a name="other-ways-to-manage-devices-and-apps"></a>デバイスとアプリを管理するその他の方法

モバイルアプリ管理 (MAM) が必要なのは、自分のデバイスで作業プロジェクトを更新するユーザーにとって、Intune はデバイスの登録と管理以外のオプションを提供する場合です。 Intune サブスクリプションでは、ユーザーのデバイスが Intune に登録されていない場合でも、Azure portal を使用して MAM ポリシーを設定できます。 詳細については、「 [アプリ保護ポリシーの概要](https://go.microsoft.com/fwlink/?LinkId=2132517)」を参照してください。

## <a name="related-topics"></a>関連項目

[基本的なモビリティとセキュリティの設定](set-up.md)

[基本的なモビリティとセキュリティを使用してモバイルデバイスを登録する](enroll-your-mobile-device.md)

[Microsoft 365 用のモバイルデバイス管理に登録されているデバイスの管理](manage-enrolled-devices.md)

[基本的なモビリティとセキュリティによって管理されるデバイスの詳細を取得する](get-details-about-managed-devices.md)
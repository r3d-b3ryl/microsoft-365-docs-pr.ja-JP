---
title: Microsoft 365 Lighthouseのエラー メッセージと問題のトラブルシューティング
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: crimora
audience: Admin
ms.topic: troubleshooting
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、エラー メッセージと問題のトラブルシューティングに関するヘルプを参照してください。
ms.openlocfilehash: a93e6816effdc68253c4ec465fa79213258d7581
ms.sourcegitcommit: f181e110cdb983788a86f30d5bb018e53c83e64d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057831"
---
# <a name="troubleshoot-error-messages-and-problems-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseのエラー メッセージと問題のトラブルシューティング

この記事では、Microsoft 365 Lighthouseの使用中に発生する可能性のあるエラー メッセージと問題について説明し、それらを解決するために実行できるトラブルシューティング手順について説明します。

## <a name="partner-onboarding"></a>パートナーのオンボード

### <a name="message-when-trying-to-access-lighthouse-microsoft-365-lighthouse-doesnt-support-indirect-providers-at-this-time-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>Lighthouse にアクセスしようとするときのメッセージ: "現時点では間接プロバイダーをサポートしていないMicrosoft 365 Lighthouse、このサービスを使用するには間接リセラーまたは直接請求パートナーである必要があります"

**原因：** 間接請求パートナーとして Lighthouse にアクセスしようとしました。 現時点では、Lighthouse は間接リセラーと直接請求パートナーのみをサポートしています。

**解像 度：** 資格と要件の完全な一覧については、「[Microsoft 365 Lighthouseの要件」を](m365-lighthouse-requirements.md)参照してください。 間接プロバイダーではなく、エラーでこのメッセージを受け取ったと思われる場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。

### <a name="message-when-trying-to-access-lighthouse-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>Lighthouse にアクセスしようとするときのメッセージ: "このサービスを使用するには、間接リセラーまたは直接請求パートナーである必要があります"

**原因：** Lighthouse にアクセスしようとしましたが、Microsoft パートナーではありません。 Lighthouse を使用するには、間接リセラーまたは直接請求パートナーとしてクラウド ソリューション プロバイダー (CSP) プログラムに登録されている必要があります。

**解像 度：** 資格と要件の完全な一覧については、「[Microsoft 365 Lighthouseの要件」を](m365-lighthouse-requirements.md)参照してください。 Lighthouse にアクセスする資格があり、エラーでこのメッセージが表示されたと思われる場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。

### <a name="message-when-signing-in-to-lighthouse-accept-the-partner-amendment"></a>Lighthouse にサインインするときのメッセージ: "パートナーの修正に同意する"

**原因：** パートナー テナントのグローバル管理者がパートナーの修正に署名する前に、Lighthouse にアクセスしようとしました。

**解像 度：** グローバル管理者は、Lighthouse にアクセスして作業する前に、Lighthouse にサインインし、パートナーの修正に同意する必要があります。 グローバル管理者が修正に署名した後もエラーが解決しない場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。

## <a name="customer-tenant-onboarding"></a>顧客テナントのオンボード  

### <a name="customer-tenants-show-a-status-other-than-active-in-the-tenant-list"></a>顧客テナントは、テナントの一覧に "アクティブ" 以外の状態を表示します。  

**原因：** 顧客テナントは、次の条件を満たしていません。

- カスタマー テナントを管理できるようにするには、マネージド サービス プロバイダー (MSP) に対して委任されたアクセスが設定されている必要があります*
- 少なくとも 1 つのMicrosoft 365 Business Premium、Microsoft 365 E3、Microsoft 365 E5、Windows 365 Business、またはMicrosoft Defender for Businessライセンス
- ライセンスを持つユーザーが 2500 人以下である必要があります 

**解像 度：** 次の表では、アクションを必要とするさまざまなテナントの状態と、それらを解決する方法について説明します。

顧客を Lighthouse にオンボードするには、詳細な代理管理特権 (GDAP) と間接リセラー関係、または代理管理特権 (DAP) リレーションシップのいずれかが必要です。 顧客テナントに DAP と GDAP が共存する場合、GDAP 対応のセキュリティ グループの MSP 技術者には、GDAP アクセス許可が優先されます。 近日、GDAP のみのリレーションシップ (間接リセラー関係なし) を持つお客様は、Lighthouse にオンボードできるようになります。<br><br>

| 状態 | 説明 | 解決方法 |
|--|--|--|
| 非アクティブ | テナントは MSP の要求でオフボードされ、ライトハウスで管理されなくなりました。 | テナントを再アクティブ化する必要があります。 [ **テナント** ] ページで、再アクティブ化するテナントの横にある 3 つのドット (その他のアクション) を選択し、[ **テナントのアクティブ化**] を選択します。 最初の顧客データが Lighthouse に表示されるまでに 24 ~ 48 時間かかる場合があります。 |
| 不適格 - DAP または GDAP が設定されていません | テナントで設定された DAP または GDAP および間接リセラー管理特権はありません。これは Lighthouse で必要です。 | Microsoft パートナー センターで DAP または GDAP および間接リセラーの管理者特権を設定します。 |
| 不適格 - 必要なライセンスがありません | テナントに必要なライセンスがありません。 少なくとも 1 つのMicrosoft 365 Business Premium、Microsoft 365 E3、Microsoft 365 E5、またはMicrosoft Defender for Businessライセンスが必要です。 | テナントに少なくとも 1 つのMicrosoft 365 Business Premium、Microsoft 365 E3、Microsoft 365 E5、Windows 365 Business、またはMicrosoft Defender for Businessライセンスが割り当てられます。 |
| 不適格 - ユーザー数が超過しました | テナントには、Lighthouse で許可されているライセンスユーザーの最大数が 2,500 人を超えています。 | テナントに 2500 を超えるライセンス ユーザーが含まれていないことを確認します。 |
| 不適格 - geo チェックに失敗しました | ユーザーと顧客は、Lighthouse で必要とされる同じ地理的リージョンに存在しません。 | 顧客が地理的リージョンに存在することを確認します。 そうでない場合は、Lighthouse でテナントを管理することはできません。 |
| 処理中 | Lighthouse はテナントを検出しましたが、まだオンボード中です。 | Lighthouse がテナントのオンボードを完了するまでに 48 時間かかります。 |

顧客テナントがオンボード条件を満たしていて、まだ Lighthouse で **アクティブ** として表示されないことを確認した場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。

## <a name="access-and-permissions"></a>アクセスとアクセス許可

### <a name="message-when-trying-to-access-lighthouse-not-authorized-or-insufficient-privileges-or-access-restriction-insufficient-or-lack-of-permissions-is-causing-access-restriction"></a>Lighthouse にアクセスしようとするときのメッセージ: "承認されていません" または "権限が不十分" または "アクセス制限: アクセス制限が不足しているか、アクセス制限の原因になっている" 

**原因：** Azure AD の適切なセキュリティ グループに属していないか、または Lighthouse にアクセスできるようにパートナー センターで正しいロールが割り当てられていない。

**解像 度：** 適切なアクセス許可を持つパートナー テナントの管理者が、Azure AD の適切な GDAP セキュリティ グループに割り当てられ、パートナー センターで正しいロールが割り当てられていることを確認します。 また、Lighthouse の一部のアクションでは、グローバル管理者である必要があることに注意してください。GDAP ロールと各ロールで実行できる操作の詳細については、「[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md)」を参照してください。 GDAP のすべての Azure AD 組み込みロールとアクセス許可の詳細については、「 [Azure AD 組み込みロール](/azure/active-directory/roles/permissions-reference)」を参照してください。

DAP リレーションシップを持つ顧客の場合、パートナー管理者は、パートナー センターの管理者エージェントまたはヘルプデスク エージェントロールにユーザーを割り当てる必要があります。 すべてのパートナー センターの役割とアクセス許可の詳細については、「 [ユーザーにロールとアクセス許可を割り当てる」を](/partner-center/permissions-overview)参照してください。

### <a name="i-dont-see-complete-data-in-certain-areas-of-lighthouse-or-i-cant-perform-certain-tasks-or-i-cant-access-certain-tenants"></a>Lighthouse の特定の領域に完全なデータが表示されない、または特定のタスクを実行できない、または特定のテナントにアクセスできない

**原因：** 現在の Azure AD セキュリティ グループに割り当てられているロールに基づいて GDAP アクセスが制限されています。

**解像 度：** 適切なアクセス許可を持つパートナー テナントの管理者が、Azure AD の正しい GDAP セキュリティ グループに割り当てられていることを確認します。 また、Lighthouse の一部のアクションでは、グローバル管理者である必要があることに注意してください。GDAP ロールと各ロールで実行できる操作の詳細については、「[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md)」を参照してください。 GDAP のすべての Azure AD 組み込みロールとアクセス許可の詳細については、「 [Azure AD 組み込みロール](/azure/active-directory/roles/permissions-reference)」を参照してください。

## <a name="customer-tenant-management"></a>顧客テナント管理  

### <a name="customer-tenant-has-no-data-showing-in-lighthouse"></a>顧客テナントに、Lighthouse にデータが表示されない

**原因：** テナントのオンボードが完了する前に、Lighthouse でデータを表示しようとしています。

**解像 度：** 最初の顧客データが Lighthouse に表示されるまでに 24 ~ 48 時間かかる場合があります。 テナントのオンボードから 48 時間以上が経過してもテナント データを表示または読み込むことができない場合、または以前に可能だったデータを表示または読み込むことができない場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。 関連するネットワーク ログと、変更された可能性があるオプションの一覧を提供する準備をしてください。

### <a name="customer-tenant-data-isnt-updating-after-making-changes-in-the-customer-tenant"></a>顧客テナントで変更を加えても、顧客テナント データが更新されない

**原因：** 顧客テナント内で行った変更は、Lighthouse の顧客テナント データと同期するのに最大で 4 時間かかる場合があります。

**解像 度：** 4 時間以上経過しても、顧客テナント データが Lighthouse で更新されない場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。 顧客テナント情報を提供する準備をしてください。

### <a name="message-when-applying-a-baseline-to-a-customer-tenant-process-error-occurred"></a>顧客テナントにベースラインを適用するときのメッセージ:"プロセス エラーが発生しました"  

**原因：** 顧客テナント内のMicrosoft Intuneの構成が正常に完了しませんでした。

**解像 度：** 顧客テナント内のIntuneの基本的な構成手順が完了したことを確認します。 カスタマー テナントの Intune構成が完了したことを確認した後も問題が解決しない場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。

### <a name="cant-access-partner-tenant-data-in-lighthouse"></a>Lighthouse でパートナー テナント データにアクセスできない

**原因**: Lighthouse では *、顧客* テナントの表示と管理のみがサポートされます。 現在、 *パートナー* テナントの表示と管理はサポートされていません。

**解像 度：** パートナー テナントの表示と管理に使用していた方法を引き続き使用します。

## <a name="device-and-threat-management"></a>デバイスと脅威の管理 

### <a name="i-dont-see-any-customer-tenant-data-on-the-device-compliance-and-threat-management-pages-of-lighthouse"></a>Lighthouse のデバイス コンプライアンスと脅威管理ページに顧客テナント データが表示されない

**原因 1:** 顧客テナントがIntuneへのオンボードを完了していません。 顧客テナントデータは、顧客テナントがIntuneへのオンボードを完了するまで、Lighthouse のデバイス コンプライアンスまたは脅威管理ページでは使用できません。

**解像 度：** データを表示しようとしている顧客テナントが、Intuneへのオンボードを完了したことを確認します。 Intuneでオンボードが完了したら、デバイス データが Lighthouse に表示されるように 4 時間かかります。

**原因 2:** 顧客テナントは最近 Lighthouse にオンボードされ、データはまだ Lighthouse に読み込まれています。

**解像 度：** 顧客テナントが Lighthouse にオンボードされたら、最初の顧客データが表示されるように 24 ~ 48 時間待ちます。

**原因 3:** 顧客テナント デバイスは新しく、デバイス データはまだ Lighthouse で読み込まれています。

**解像 度：** テナント デバイスが追加されたら、デバイス データが Lighthouse に表示されるのに 4 時間を許可します。

解決手順に従った後、デバイスコンプライアンスと脅威の管理ページにデータがまだ表示されない場合は、サポートにお問い合わせください。 詳細については、「[Microsoft 365 Lighthouseのヘルプとサポートを受ける」を](m365-lighthouse-get-help-and-support.md)参照してください。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseに関する既知の問題](m365-lighthouse-known-issues.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)\
[Microsoft 365 Lighthouseのヘルプとサポートを受ける](m365-lighthouse-get-help-and-support.md) (記事)

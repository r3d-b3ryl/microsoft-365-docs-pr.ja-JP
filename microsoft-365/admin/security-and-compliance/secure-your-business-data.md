---
title: データをセキュリティで保護する上位 10 の方法 - 中小企業向けのベスト プラクティス
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.date: 08/24/2022
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkDEFENDER
- adminvideo
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
description: ランサムウェア、フィッシング、悪意のある添付ファイルなど、ビジネスを保護する上位 10 の方法について説明します。
ms.openlocfilehash: 1672b0c5233f1dce6f95847a986ea43ed03e15dc
ms.sourcegitcommit: e6595be36bbaba244439bd59dbae935e2b258ded
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2022
ms.locfileid: "67450193"
---
# <a name="top-10-ways-to-secure-your-data---best-practices-for-small-and-medium-sized-businesses"></a>データをセキュリティで保護する上位 10 の方法 - 中小企業向けのベスト プラクティス

**適用対象**

- Microsoft 365 Business Basic
- Microsoft 365 Business Standard
- Microsoft 365 Business Premium

Microsoft 365 for Business プランには、改ざん、スパム対策、マルウェア対策などのセキュリティ機能が含まれます。 Microsoft 365 Business Premiumには、デバイス管理、高度な脅威保護、情報保護など、より多くの機能が含まれています。 この記事では、ビジネス データをセキュリティで保護するために実行できる手順について説明し、 [Microsoft 365 のビジネス プラン全体の機能を比較](#comparing-microsoft-365-for-business-plans)します。

:::image type="content" source="../../media/top-10-ways-secure-data.png" alt-text="ビジネス データをセキュリティで保護する上位 10 の方法を示す図。":::

| 手順 | タスク | 説明 |
|:--:|:---|:---|
| 1 | **[多要素認証を使用](multi-factor-authentication-microsoft-365.md)** します。 | [多要素認証](multi-factor-authentication-microsoft-365.md) (MFA) は、2 段階認証とも呼ばれ、ユーザーが Microsoft 365 にサインインするために携帯電話でコードまたは認証アプリを使用する必要があり、ビジネス データを保護するための重要な最初のステップです。 MFA を使用すると、ハッカーがパスワードを知っている場合に引き継ぐのを防ぐことができます。<br/><br/>[セキュリティの既定値と MFA を](../../business-premium/m365bp-conditional-access.md)参照してください。 |
| 2 | **[管理者アカウントを保護します](../../business-premium/m365bp-protect-admin-accounts.md)**。 | 管理者アカウント (管理者とも呼ばれます) には特権が昇格されているため、これらのアカウントはサイバー攻撃の影響を受けやすくなります。 ビジネスに適した数の管理者アカウントとユーザー アカウントを設定して管理する必要があります。 また、最小限の特権の情報セキュリティ原則に従うこともお勧めします。つまり、ユーザーとアプリケーションには、ジョブの実行に必要なデータと操作へのアクセスのみを許可する必要があります。 <br/><br/>[「管理者アカウントを保護する」を参照してください](../../business-premium/m365bp-protect-admin-accounts.md)。 |
| 3 | **[事前設定されたセキュリティ ポリシーを使用します](../../business-premium/m365bp-increase-protection.md)**。 | サブスクリプションには、スパム対策、マルウェア対策、フィッシング対策の保護のためのおすすめの設定を使用する[事前設定されたセキュリティ ポリシー](../../security/office-365-security/preset-security-policies.md)が含まれています。 <br/><br/>[「マルウェアやその他のサイバー脅威から保護する」を](../../business-premium/m365bp-increase-protection.md)参照してください。 |
| 4 | **[すべてのデバイスを保護します](../../business-premium/m365bp-devices-overview.md)**。 | すべてのデバイスはネットワークへの攻撃の可能性があり、個人が所有しているが仕事に使用されるデバイスであっても、適切に構成する必要があります。 <br/><br/>次の記事をご覧ください。 <br/>- [ユーザーが自分のデバイスで MFA を設定するのに役立つ](https://support.microsoft.com/office/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14)<br/>- [管理されていない Windows コンピューターと Mac コンピューターを保護する](../../business-premium/m365bp-protect-pcs-macs.md) <br/>- [マネージド デバイスを設定する](../../business-premium/m365bp-managed-devices-setup.md) (Microsoft 365 Business PremiumまたはMicrosoft Defender for Businessが必要) |
| 5 | **[メールのベスト プラクティスに関する全員をトレーニングします](../../business-premium/m365bp-avoid-phishing-and-attacks.md)**。 | Emailには、無害な通信として隠された悪意のある攻撃が含まれている可能性があります。 Email システムは特に脆弱です。電子メールは組織内のすべてのユーザーによって処理され、安全性は人間がそれらの通信に対して一貫して良好な意思決定を行う必要があるためです。 スパムや迷惑メール、フィッシング詐欺、スプーフィング、マルウェアをメールで監視する方法を全員に知ってしてもらう。 <br/><br/>[「フィッシングやその他の攻撃から身を守る](../../business-premium/m365bp-avoid-phishing-and-attacks.md)」を参照してください。 |
| 6 | **[共同作業と共有には Microsoft Teams を使用](../../business-premium/m365bp-collaborate-share-securely.md)** します。 | 共同作業と安全な共有を行う最善の方法は、Microsoft Teams を使用することです。 Microsoft Teams を使用すれば、すべてのファイルと通信が保護された環境にあることになり、安全でない方法で外部に保存されることはありません。<br/><br/> 次の記事をご覧ください。 <br/>- [共同作業に Microsoft Teams を使用する](../../business-premium/create-teams-for-collaboration.md) <br/>- [Microsoft Teams との会議を設定する](../../business-premium/set-up-meetings.md) <br/>- [安全な環境でファイルとビデオを共有する](../../business-premium/share-files-and-videos.md) |
| 7  | **[SharePoint と OneDrive のファイルとフォルダーの共有設定を設定します](../../business-premium/m365bp-increase-protection.md)**。 | SharePoint と OneDrive の既定の共有レベルは、使用する必要があるよりも許容レベルに設定されている場合があります。 ビジネスをより適切に保護するために、既定の設定を変更し、必要に応じて確認することをお勧めします。 ジョブを実行するために必要なアクセス権のみをユーザーに付与します。 <br/><br/>[SharePoint と OneDrive のファイルとフォルダーの共有設定の設定に関](../../business-premium/m365bp-increase-protection.md#set-sharing-settings-for-sharepoint-and-onedrive-files-and-folders)するページを参照してください。 |
| 8  | **[デバイスでMicrosoft 365 Appsを使用します](https://support.microsoft.com/topic/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27)**。 | Outlook とMicrosoft 365 Apps (Office アプリとも呼ばれます) を使用すると、ユーザーはデバイス間で生産性と安全性を高めることができます。 アプリの Web バージョンまたはデスクトップ バージョンを使用している場合でも、1 つのデバイスでドキュメントを開始し、後で別のデバイスで取得できます。 ファイルを電子メールの添付ファイルとして送信する代わりに、SharePoint または OneDrive に格納されているドキュメントへのリンクを共有できます。 <br/><br/>次の記事をご覧ください。 <br/>- [すべてのデバイスに Office アプリをインストールします](../../business-premium/m365bp-install-office-apps.md)。<br/>- [Office と Microsoft 365 でユーザーをトレーニングする](https://support.microsoft.com/topic/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27) |
| 9  | **[ビジネスの予定表共有を管理します](../../business-premium/m365bp-increase-protection.md#manage-calendar-sharing)**。 | 組織内のユーザーが予定表を適切に共有し、共同作業を改善できるように支援できます。 共有する詳細を空き時間のみに制限するなど、共有できる詳細レベルを管理できます。 <br/><br/>[予定表共有の管理](../../business-premium/m365bp-increase-protection.md#manage-calendar-sharing)に関するページを参照してください。 |
| 10 | **[環境を維持します](../../business-premium/m365bp-maintain-environment.md)**。 | Microsoft 365 for Business の初期セットアップと構成が完了したら、組織にはメンテナンスと運用計画が必要です。 従業員が行き来するときに、ユーザーを追加または削除したり、パスワードをリセットしたり、デバイスを出荷時の設定にリセットしたりする必要があります。 また、ユーザーが自分の仕事を行うために必要なアクセス権のみを持っていることを確認する必要もあります。 <br/><br/>「 [環境の保守」を参照してください](../../business-premium/m365bp-maintain-environment.md)。 |

## <a name="comparing-microsoft-365-for-business-plans"></a>ビジネス プランの Microsoft 365 の比較

Microsoft 365 for Business プランには、セキュリティで保護された電子メール、コラボレーション、ファイル ストレージ用の Microsoft Exchange、Microsoft Teams、SharePoint、OneDrive が含まれます。 これらのプランには、改ざん、マルウェア対策、スパム対策の保護も含まれます。 Microsoft 365 Business Premiumを使用すると、デバイス管理、高度な脅威保護、情報保護など、より多くの機能を利用できます。 

次の表では、ビジネス プランの Microsoft 365 の機能を比較します。 

| 機能 | [Microsoft 365 Business Basic](../setup/setup-business-basic.md) | [Microsoft 365 Business Standard](../setup/setup-business-standard.md) | [Microsoft 365 Business Premium](../../business-premium/index.md) |
|:---|:--:|:--:|:--:|
| **Outlook と Web/mobile バージョンの Office アプリ** <br/>Word、Excel、PowerPoint | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| **デスクトップ バージョンの Office アプリ**<br/>Word、Excel、PowerPoint、Publisher、Access <sup>[[注 1 を参照](#fn1)]</sup> |  | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| **セキュリティで保護された通信、コラボレーション、ファイル ストレージ**<br/>Microsoft Teams、Exchange、OneDrive、SharePoint | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| メールの **スパム対策、改ざん防止、マルウェア対策の保護** <br/>[Exchange Online Protection](../../security/office-365-security/exchange-online-protection-overview.md) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| **モバイル デバイス管理** とモバイル アプリ管理 <br/>[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) | <sup>注 [[2](#fn2)] を</sup>参照してください | <sup>注 [[2](#fn2)] を</sup>参照してください | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 次世代の保護、ファイアウォール、攻撃面の削減、自動調査と対応などを備えた **高度なデバイス セキュリティ** <br/>[Defender for Business](../../security/defender-business/mdb-overview.md) | <sup>メモ [[3](#fn3)] を</sup>参照してください  | <sup>メモ [[3](#fn3)] を</sup>参照してください | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| **高度な** フィッシング対策、安全なリンク、安全な添付ファイル、リアルタイムの検出を使用した電子メールとドキュメントの高度な保護<br/>[Microsoft Defender for Office 365 プラン 1](../../security/office-365-security/defender-for-office-365.md) | メモ <sup>[[4](#fn4)]</sup> を参照してください | メモ <sup>[[4](#fn4)]</sup> を参照してください | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | 
| 機密情報を検出、分類、保護、管理するための **情報保護機能** <br/>[Azure Information Protection](/azure/information-protection/what-is-information-protection)  | | | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |

(<a id="fn1">1</a>) Microsoft Publisher と Microsoft Access は、Windows ノート PC とデスクトップでのみ実行されます。

(<a id="fn2">2</a>) Microsoft Intuneは、特定の Microsoft 365 プランに含まれています。 基本的なモビリティとセキュリティ機能は、Microsoft 365 Business Basicと Standard の一部です。 [Basic Mobility と Security または Intuneのどちらかを選択します](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md)。

(<a id="fn3">3</a>) Defender for Business はMicrosoft 365 Business Premiumに含まれています。 また、Microsoft 365 Business BasicまたはMicrosoft 365 Business Standard用のアドオンとして購入することもできます。 「 [ビジネス向け Defender を取得する」を](/microsoft-365/security/defender-business/get-defender-business)参照してください。

(<a id="fn4">4</a>) Defender for Office 365プラン 1 はMicrosoft 365 Business Premiumに含まれます。 また、Microsoft 365 Business BasicまたはMicrosoft 365 Business Standard用のアドオンとして購入することもできます。 [プラン 1 とプラン 2 Defender for Office 365を](../../security/office-365-security/overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet)参照してください。

> [!TIP]
> 各プランに含まれる内容の詳細については、 [Microsoft 365 と Microsoft Teams での生産性の再考](https://www.microsoft.com/en-us/microsoft-365/business/compare-all-microsoft-365-business-products-b?ef_id=8c2a86ec9ea514a008c6e419e036519c:G:s&OCID=AIDcmmwf9kwzdj_SEM_8c2a86ec9ea514a008c6e419e036519c:G:s&lnkd=Bing_O365SMB_Brand&msclkid=8c2a86ec9ea514a008c6e419e036519c)に関するページを参照してください。


## <a name="see-also"></a>関連項目

- [Defender for Business とは](../../security/defender-business/mdb-overview.md)
- [Microsoft 365 Business Premium— 小規模ビジネス向けのサイバーセキュリティ](/microsoft-365/business-premium/)
- [中小企業向けの Microsoft 365 プランのセキュリティ機能を比較](../../security/defender-business/compare-mdb-m365-plans.md)する (Defender for Business とMicrosoft 365 Business Premiumの詳細については)
- [Microsoft エンドポイント のセキュリティ プランを比較](../../security/defender-endpoint/defender-endpoint-plan-1-2.md) する (デバイスのセキュリティ保護と管理用)


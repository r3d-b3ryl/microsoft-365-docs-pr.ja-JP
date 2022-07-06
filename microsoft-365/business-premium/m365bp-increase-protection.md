---
title: Microsoft 365 Business Premium の脅威に対する保護を強化する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- admindeeplinkMAC
- admindeeplinkEXCHANGE
- admindeeplinkSPO
search.appverid:
- BCS160
- MET150
description: Microsoft 365 Business Premium での保護レベルの向上に関するヘルプを表示する
ms.openlocfilehash: b5d1c7c241be8e61c7f1dcb3ccd08f9c3a0e93af
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66631939"
---
# <a name="increase-threat-protection-for-microsoft-365-business-premium"></a>Microsoft 365 Business Premium の脅威に対する保護を強化する

この目的では、Microsoft 365 Business Premium を使用して脅威に対する保護を強化します。 フィッシング、マルウェア、その他の脅威からビジネスを保護することが重要です。 この記事には、次の情報が含まれています。

- セットアップと構成に多くの時間を節約できる[事前設定済みのセキュリティ ポリシー](#review-and-apply-preset-security-policies)。
- ビジネス ニーズに合わせて定義できる[カスタム セキュリティ ポリシー](#create-custom-security-policies)。
- [SharePoint と OneDrive ファイルとフォルダーの共有設定を調整する方法](#set-sharing-settings-for-sharepoint-and-onedrive-files-and-folders)。
- 特定のファイルとその使用方法を監視する[アラート ポリシー](#review-your-alert-policies)。

## <a name="review-and-apply-preset-security-policies"></a>事前設定されたセキュリティ ポリシーを確認して適用する

サブスクリプションには、スパム対策、マルウェア対策、フィッシング対策の保護のためのおすすめの設定を使用する[事前設定されたセキュリティ ポリシー](../security/office-365-security/preset-security-policies.md)が含まれています。 既定では、組み込みの保護が有効になっています。ただし、セキュリティを強化するために標準または厳格な保護を適用することを検討してください。

:::image type="content" source="media/m365bp-presetsecuritypolicies.png" alt-text="事前設定されたセキュリティ ポリシーを示すスクリーンショット。":::

> [!NOTE]
> 事前設定されたセキュリティ ポリシーは、[セキュリティの既定値](m365bp-conditional-access.md#security-defaults)と同じではありません。 通常は、最初にセキュリティの既定値 *または*[条件付きアクセス](m365bp-conditional-access.md#conditional-access)*のいずれかを* 使用し、次にセキュリティ ポリシーを追加します。 [事前設定されたセキュリティ ポリシー](#what-are-preset-security-policies)により、セキュリティ ポリシーを追加するプロセスが簡略化されます。 [独自の返信フォームを追加](#create-custom-security-policies)することもできます。 

### <a name="what-are-preset-security-policies"></a>事前設定されたセキュリティ ポリシーとは?

事前設定されたセキュリティ ポリシーにより、メールとコラボレーション コンテンツが保護されます。これらのポリシーは、次の要素で構成されます。

- 保護のレベルを決定する *プロファイル*
- *ポリシー* (スパム対策、マルウェア対策、フィッシング詐欺対策、スプーフィング設定、偽装、安全な添付ファイル、安全なリンクなど)
- *ポリシー設定* (ポリシーや例外を受け取るグループ、ユーザー、ドメインなど)

次の表は、保護と事前設定されたポリシーの種類のレベルをまとめたものです。

| 保護レベル | 説明 |
|:---|:---|
| **標準の保護** <br/>(*ほとんどの企業に推奨*) | 標準の保護では、ほとんどのユーザーに適したベースライン保護プロファイルが使用されます。 標準の保護には、スパム対策、マルウェア対策、フィッシング詐欺対策、スプーフィング設定、偽装設定、安全なリンク、安全な添付ファイル ポリシーが含まれます。  |
| **厳密な保護**  | 厳密な保護には、標準保護と同じ種類のポリシーが含まれていますが、より厳しい設定が含まれています。 ビジネスで追加のセキュリティ要件または規制を満たす必要がある場合は、少なくとも優先度の高いユーザーまたは高い価値のターゲットに厳格な保護を適用することを検討してください。 |
| **組み込みの保護** | メール内の悪意のあるリンクや添付ファイルから保護します。 既定では、組み込みの保護が有効になり、すべてのユーザーに適用されます。  |

> [!TIP]
> ユーザー、グループ、ドメインを指定して事前設定ポリシーを受け取ることができます。また、特定の例外を定義することはできますが、事前設定ポリシー自体を変更することはできません。 セキュリティ ポリシーに異なる設定を使用する場合は、会社のニーズに合わせて独自のカスタム ポリシーを作成できます。

### <a name="policy-order-of-priority"></a>優先度のポリシーの順序

ユーザーに複数のポリシーが割り当てられている場合は、優先度の順序を使用してポリシーを適用します。優先度の順序は次のように機能します。

1. **厳密な保護** には、最も高い優先度があり、他のすべてのポリシーをオーバーライドします。

1. **標準の保護** 

1. **カスタム セキュリティ ポリシー**

1. **組み込みの保護** には最も低い優先度が与えられ、厳格な保護、標準保護、およびカスタム ポリシーによってオーバーライドされます。

厳密な保護は他のすべてのポリシーをオーバーライドし、組み込みの保護は他のポリシーによってオーバーライドされます。 

事前設定されたセキュリティ ポリシーの詳細については、「[事前設定されたセキュリティ ポリシーの構成内容](../security/office-365-security/preset-security-policies.md#what-preset-security-policies-are-made-of)」を参照してください。

### <a name="how-do-i-assign-preset-security-policies-to-users"></a>事前設定されたセキュリティ ポリシーをユーザーに割り当てる操作方法

> [!IMPORTANT]
> 開始する前に、次のロールのうちのいずれかが Exchange Online に割り当てられていることを確認します (サブスクリプションに含まれています)。
> 
> - グローバル管理者
> - 組織の管理
> - セキュリティ管理者
> 
> 詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」と「[役割グループの管理](../admin/add-users/about-admin-roles.md)」を参照してください。

事前設定されたセキュリティ ポリシーを割り当てるには、次の手順に従います:

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

1. **[テンプレート ポリシー]** セクションで、**[メールとコラボレーション]** \> **[ポリシーとルール]** \> **[脅威に対するポリシー]** \> **[DKIM]** に移動します。 (**[事前設定セキュリティ ポリシー]** ページに直接移動するには、<https://security.microsoft.com/presetSecurityPolicies> を使用します。)

1. **[事前設定セキュリティ ポリシー**] ページの [**標準保護**] セクションまたは [**厳格な保護**] セクションで、トグルを **[無効]** から **[有効]** に変更し、[**管理**] を選択します。

1. **[標準保護の適用]** または **[厳格な保護の適用]** ウィザードはポップアップで開始されます。 **[EOP 保護の適用先**] ページで、ポリシーが適用される内部受信者 (受信者の条件) を特定します。
   - **Users**
   - **グループ**
   - **ドメイン**

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、値の横にあるアイコンの **[削除]** をクリックします。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) だけを入力すると、使用可能なすべての値が表示されます。

   除外を指定するには、**[これらのユーザー、グループ、ドメインを除外]** チェック ボックスをオンにし、除外するユーザー、グループ、またはドメインを指定します。

   完了したら、**[次へ]** を選択します。

1. **[Defender for Office 365 保護の適用先]** ページで、ポリシーが適用される内部受信者 (受信者の条件) を特定します。 前の手順で行ったのと同じように、ユーザー、グループ、ドメインを指定します。

   完了したら、**[次へ]** をクリックします。

1. **[変更の確認と確認]** ページで、選択内容を確認し、**[確認]** を選択します。

> [!TIP]
> 事前設定されたセキュリティ ポリシーの割り当ての詳細については、次の記事を参照してください:
> - [事前設定されたセキュリティ ポリシーをユーザーに割り当てる](../security/office-365-security/preset-security-policies.md#assign-preset-security-policies-to-users)
> - [メールおよびコラボレーション コンテンツの推奨設定](../security/office-365-security/recommended-settings-for-eop-and-office365.md) (Exchange Online Protection、Microsoft Defender for Office 365 プラン 1 を含む Microsoft 365 Business Premium)

## <a name="create-custom-security-policies"></a>カスタム セキュリティ ポリシーの作成

この記事で前述した [事前設定済みのセキュリティ ポリシー](#what-are-preset-security-policies)は、ほとんどの企業に強力な保護を提供します。 ただし、事前設定されたセキュリティ ポリシーのみの使用に限定されません。 会社のニーズに合わせて独自のカスタム セキュリティ ポリシーを定義できます。 

クイック スタート ガイド「[脅威ｎ対する保護](../security/office-365-security/protect-against-threats.md)」を使用して、独自のカスタム ポリシーの作成を開始します。 このガイダンスでは、独自のセキュリティ ポリシーを設定する方法だけでなく、次の開始点として使用する推奨設定も提供されます。

- [マルウェア対策保護](../security/office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [高度なフィッシング対策保護](../security/office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [スパム対策保護](../security/office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [安全なリンク、安全な添付ファイル](../security/office-365-security/protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

## <a name="set-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>SharePoint ファイルと OneDrive ファイルとフォルダーの共有設定を設定する

既定では、共有レベルは、SharePoint と OneDrive の両方で最も許容されるレベルに設定されます。 ビジネスをより適切に保護するために、既定の設定を変更することをお勧めします。

1. <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">SharePoint 管理センターの **[共有]**</a> に移動し、[組織の管理者権限](/sharepoint/sharepoint-admin-role)を持つアカウントでサインインします。

1. **[外部共有]** で、共有のレベルを指定します。 (外部共有を防ぐために **[最小許容]** を使用することをお勧めします)。

1. **[ファイルとフォルダーのリンク]** で、オプション ( **[特定のユーザー**] など) を選択します。 次に、共有リンクに対して既定で表示または編集のアクセス許可を付与するかどうかを選択します (**ビュー** など)。

1. **[その他の設定]** で、使用するオプションを選択します。

1. 次に、**[保存]** を選択します。

> [!TIP]
> 詳細については、「[共有設定を管理する](/sharepoint/turn-external-sharing-on-or-off)」を参照してください。

## <a name="review-your-alert-policies"></a>アラート ポリシーを確認する

アラート ポリシーは、ユーザーと管理者のアクティビティ、潜在的なマルウェアの脅威、ビジネスにおけるデータ損失インシデントを追跡するために役立ちます。 サブスクリプションには一連の既定のポリシーが含まれていますが、カスタム ポリシーを作成することもできます。 たとえば、他のユーザーに外部共用させたくない重要なファイルを SharePoint に保存する場合は、他のユーザーが共有した場合にアラートを表示する通知を作成できます。

次の図は、Microsoft 365 Business Premium に含まれる既定のポリシーの一部を示しています。

![Microsoft 365 に含まれる既定のアラート ポリシー。](../media/alertpolicies.png)

### <a name="view-your-alert-policies"></a>アラート ポリシーを表示する

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) で Microsoft Purview コンプライアンス ポータルに移動してサインインします。

1. ナビゲーション ウィンドウで **[ポリシー]** を選択し、**[アラート ポリシー]** を選択します。

1. 個々のポリシーを選択して詳細を表示するか、ポリシーを編集します。 次の図は、1 つのポリシーが選択されたアラート ポリシーの一覧を示しています。

   :::image type="content" source="media/selected-alert-policy.png" lightbox="media/selected-alert-policy.png" alt-text="選択したアラート ポリシーを示すスクリーンショット。":::

> [!TIP]
> 詳細については、「[アラート ポリシー](../compliance/alert-policies.md)」を参照してください。

### <a name="how-to-view-alerts"></a>アラートを表示する方法

特定のアラートに応じて、Microsoft 365 Defender ポータルまたは Microsoft Purview コンプライアンス ポータルでアラートを表示できます。

| アラートの種類。  | 操作  |
|---------|---------|
| ユーザーが悪意のあるリンクをクリックしたとき、電子メールがマルウェアまたはフィッシングとして報告されたとき、またはデバイスがマルウェアが含まれていると検出された場合などのセキュリティ アラート     | <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、**[メールと共同作業]** で **[ポリシーとルール]** > **[アラート ポリシー]** の順に選択します。または、<https://security.microsoft.com/alertpolicies> に直接移動することもできます。 |
| ユーザーが機密情報を共有する場合 (データ損失防止アラート) や、異常な量の外部ファイル共有がある場合などのコンプライアンス アラート (情報ガバナンス アラート)    | <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>に移動し、**[ポリシー]** > **[アラート]** > **[アラート ポリシー]** の順に選択します。  |

詳細については、「[アラートの表示](../compliance/alert-policies.md#view-alerts)」を参照してください。

## <a name="disable-or-manage-calendar-sharing"></a>予定表共有を無効または管理する

組織内のユーザーが予定表を共有できないようにすることができます。 また、共有できる詳細レベルを管理することもできます。 たとえば、空き時間情報の共有のみに制限することができます。

1. [Microsoft 365 管理センターで [組織の設定]](https://go.microsoft.com/fwlink/p/?linkid=2053743) に移動し、サインインします。

1. **[Outlook カレンダー]** を選択し、組織内のユーザーが、Office 365 または Exchange を持つ外部のユーザーと予定表を共有できるか、またはすべてのユーザーと予定表を共有できるかを選択します。

   **[外部共有]** オプションをオフにすることをお勧めします。

   [すべてのユーザーと共有] オプションを選択した場合は、空き時間情報のみを共有させることもできます。

1. ページの下部にある **[変更の保存]** を選択します。

   次の図は、予定表の共有が許可されない状態を示しています。

   ![予定表の外部共有不許可を示すスクリーンショット。](../media/nocalendarsharing.png)

   次の図は、空き時間情報のみを含むメール リンクで予定表共有が許可されている場合の設定を示しています。

   ![予定表の空き時間情報をすべてのユーザーと共有する設定を示すスクリーンショット。](../media/sharefreebusy.png)

ユーザーが予定表の共有を許可されている場合は、Outlook on the web から共有する方法について、[次の手順](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5)を参照してください。

## <a name="next-steps"></a>次の手順

それでは、[**これらのアンマネージド BYOD デバイスを設定**](m365bp-devices-overview.md)しましょう。

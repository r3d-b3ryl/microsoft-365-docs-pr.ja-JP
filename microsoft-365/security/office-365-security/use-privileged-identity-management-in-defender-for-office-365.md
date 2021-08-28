---
title: Defender for Office 365 の Defender Privileged Identity Management (PIM) を使用します。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/09/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365 で昇格された特権タスクを実行し、データのリスクを減らすため、Just-In-Time の時間制限付きアクセスをユーザーに付与するために PIM を統合する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d1333963f841a9d9263f44263ad43d20ec75057
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615042"
---
# <a name="privileged-identity-management-pim-and-why-to-use-it-with-microsoft-defender-for-office-365"></a>Privileged Identity Management (PIM) と Microsoft Defender for Office 365 で使用する理由

Privileged Identity Management (PIM) は、設定が完了すると、ユーザーが限定時間 (タイム ボックス化された期間とよばれることもあります)、特定のタスクを実行できるデータにアクセスできるようにさせる Azure 機能です。 このアクセスは、必要なアクションを実行するために 'just-in-time' を与えられた後、取り消されます。 PIM は、ユーザーが機密データに対するアクセスと時間を制限し、データや他の設定に長期的にアクセスできる特権管理アカウントと比較して、露出リスクを軽減します。 では、この機能 (PIM) を Microsoft Defender for Office 365 と組み合わせて使用するにはどうすればいいでしょうか?

> [!TIP]
> PIM アクセスのスコープは役割と ID レベルであり、複数のタスクを完了できます。 タスク レベルでスコープが設定されている Priviledged Access Management (PAM) と混同しないでください。

## <a name="steps-to-use-pim-to-grant-just-in-time-access-to-defender-for-office-365-related-tasks"></a>PIM を使用して、関連するタスクに対して Defender for Office 365 への just-in-time アクセスを付与する手順

管理者は、Defender for Office 365 と連携するように PIM を設定することで、ユーザーが必要なアクションを実行するためのアクセスを要求するプロセスを作成します。 ユーザーは、特権の昇格の必要性を *正当化する* 必要があります。

この例では、Office 365 内で立ち上がりアクセスをゼロにできるセキュリティ チームのメンバーである "Alex" を構成しますが、通常の日々の運用に必要な役割にも、メールの削除など、頻度が低く機密性の高い操作が必要な場合のより高いレベルの特権にも昇格できます。

> [!NOTE]
> この手順では、Microsoft Defender for Office 365 で 脅威エクスプローラーを使用して電子メールを削除する機能が必要なセキュリティ アナリスト用に PIM をセットアップするために必要な手順について説明しますが、セキュリティ ポータルおよびコンプライアンス ポータル内の他の RBAC の役割にも同じ手順を使用できます。 たとえば、このプロセスは、検索やケースワークを行うのに電子情報管理に日々にアクセスする必要があるが、テナントからデータをエクスポートするための昇格された権限がたまに必要な情報作業者に使われることがあります。


***手順 1***。 サブスクリプションの Azure PIM コンソールで、ユーザー (Alex) を Azure Security Reader の役割に追加し、ライセンス認証に関連するセキュリティ設定を構成します。

1. [Azure AD 管理センター](https://aad.portal.azure.com/)にサインインし、[役割 **[Azure Active Directory]**  >  **[役割と管理者]** の順に選択します。
2. 役割の一覧で **[セキュリティ リーダー]** を選択し、**[設定]**  >  **[編集]** の順に選択します。
3. '**アクティブ化の最大期間 (時間)**' を通常の稼働日に設定し、**Azure MFA** を要求するには 'On activation (アクティブ化時)' を設定します。
4. これは、日々の操作に対する Alex の通常の特権レベルです。**[ライセンス認証時に正当性を要求する]** のチェックをオフにして、**[更新]** を選択します。
5. **[割り当ての追加]**  >  **[メンバーが選択されていない]** > 正しいメンバーを検索するための名前を選択または入力します。
6. **[選択]** ボタンをクリックして、PIM 特権用に追加する必要のあるメンバーを選択します> **[次へ]** > [割り当ての追加] ページで変更を加えず (割り当てタイプの *[適格]* と *[永続的に適格]* が既定になります)、**[割り当て]** をクリックします。

ユーザーの名前 (ここでは 「Alex」) は、次のページの [適格な割り当て] の下に表示されます。つまり、以前に構成した設定を使用して、役割に PIM を割り当てることができます。

> [!NOTE]
> Privileged Identity Management を簡単にレビューするには[このビデオ](https://www.youtube.com/watch?v=VQMAg0sa_lE)をご覧ください。

:::image type="content" source="../../media/pim-mdo-role-setting-details-for-security-reader-show-8-hour-max-activation.PNG" alt-text="必ず特権アクセス管理で、セキュリティ リーダーの役割の設定をスキャンするようにしてください。ここでは、PIM ライセンス認証の最大期間が 8 時間であるのが表示されます。":::

***手順 2***。 追加のタスクに必要な 2 番目の (昇格された) アクセス許可グループを作成し、適格性を割り当てます。

[[特権アクセス グループ]](/azure/active-directory/privileged-identity-management/groups-features) を使用して、独自のカスタム グループを作成し、権限を組み合わせたり、組織のプラクティスやニーズを満たすために必要な粒度を上げたりすることができます。

### <a name="create-a-role-group-requiring-the-permissions-we-need"></a>必要なアクセス許可を必要とする役割 グループを作成します。

セキュリティ ポータルで、必要なアクセス許可を含むカスタム役割グループを作成します。 

1. Microsoft 365 Defender ポータルを参照します ([https://security.microsoft.com) > **[アクセス許可と役割]** >、[メールとコラボレーション] の **[役割]** > **[作成]** の順に選択します。
2. 目的を表すグループ名を付けます (「検索と削除 PIM」など)。
3. メンバーを追加せずに、グループを保存して次の部分に進みます。

### <a name="create-the-security-group-in-azure-ad-for-elevated-permissions"></a>昇格されたアクセス許可用に Azure AD でセキュリティー グループを作成する

1. [Azure AD 管理センター](https://aad.portal.azure.com/)に戻り、**[Azure AD]**  >  **[グループ]**  >  **[新しいグルプ]** の順に移動します。
2. 目的を表す名前を AAD グループに付け、その時点ですぐに **所有者やメンバー は必要ありません**。
3. **”Azure AD の役割をグループに割り当て可能”** を **[はい]** にします。
4. 役割、メンバー、または所有者を追加しないで、グループを作成します。
5. 作成したグループに戻り **[特権アクセス]**  >  **[特権アクセスを有効にする]** を選択します。
6. グループ内で **[適格な割り当て]**  >  **[割り当ての追加]** > **メンバー** の役割として検索と削除を必要とするユーザーを 追加します。
7. グループの [特権アクセス] ウィンドウ内で **[設定]** を構成します。 **[メンバー]** の役割の設定を **[編集]** を選択します。
8. 組織に合わせてアクティブ化時間を変更します。 この例では、*Azure MFA*、*正当化*、および *チケット情報* が、**[更新]** を選択する為に必要です。

### <a name="nest-the-newly-created-security-group-into-the-role-group"></a>新しく作成したセキュリティ グループを役割グループに入れ子にします。

1. [セキュリティー/コンプライアンス センター PowerShell に接続](/powershell/exchange/connect-to-scc-powershell)し、次のコマンドを実行します:

    `Add-RoleGroupMember "<<Role Group Name>>" -Member "<<Azure Security Group>>"`


## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

1. 管理者アクセス権がまったくないテスト ユーザーでログインします。
2. ユーザーが日々のセキュリティ リーダーの役割をアクティブ化できる PIM に移動します。
3. 脅威エクスプローラーを使用してメールを削除しようとすると、追加のアクセス許可が必要であることを示すエラーが表示されます。
4. 2 度目は短時間の遅延の後に、PIM の役割がより昇格され、問題なくメールを削除できるようになります。

検索と削除の役割の永続的な割り当てでは、ゼロ トラスト セキュリティ イニシアチブでは保持されませんが、PIM を使用して、必要なツールセットへの Just-In-Time アクセスを許可できます。

:::image type="content" source="../../media/pim-mdo-add-the-search-and-purge-role-assignment-to-this-pim-role.PNG" alt-text="セキュリティ リーダー PIM の役割を介して追加したユーザー (Alex) が疑わしいメールを削除しようとすると、&quot;このメールに対してアクションを実行するには、検索と削除の役割が必要です&quot; というメッセージが表示されます。管理者に問い合わせて役割の割り当てを取得するか、インシデントにメールを追加します。":::

検索と削除の役割の永続的な割り当ては、ゼロ トラスト セキュリティ イニシアチブでは保持されませんが、PIM を使用して、ここでも Just-in-time アクセスを付与できます。

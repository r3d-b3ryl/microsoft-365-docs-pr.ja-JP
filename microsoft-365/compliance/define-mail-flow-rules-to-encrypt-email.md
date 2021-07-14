---
title: メール メッセージを暗号化するメール フロー ルールを定義する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理者は、メール フロー ルール (トランスポート ルール) を作成して、メール フロー ルールを使用してメッセージを暗号化および復号化Office 365 Message Encryption。
ms.openlocfilehash: 5274c2368de9825bd0568b7abd4e060e22fe9c70
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430458"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>メール メッセージを暗号化するメール フロー ルールを定義する

管理者は、Exchange Onlineメール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、送受信する電子メール メッセージを保護できます。 送信電子メール メッセージを暗号化し、組織内から送信される暗号化されたメッセージから、または組織から送信された暗号化されたメッセージへの返信から暗号化を削除するルールを設定できます。 これらのルールは、Exchange管理センター (EAC) または powerShell Exchange Online使用して作成できます。 全体的な暗号化ルールのほかに、エンド ユーザー向けの個別メッセージ暗号化のオプションの有効/無効を選択できます。

組織外の送信者からの受信メールを暗号化できない。

Active Directory RMS から Azure Information Protection に最近移行した場合は、既存のメール フロー ルールを確認して、新しい環境で引き続き動作するようにする必要があります。 また、Azure Information Protection を使用して使用可能な新しい Office 365 Message Encryption (OME) 機能を利用する場合は、既存のメール フロー ルールを更新する必要があります。 それ以外の場合、ユーザーは、新しいシームレスな OME エクスペリエンスではなく、以前の HTML 添付ファイル形式を使用する暗号化されたメールを引き続き受信します。 OME をまだセットアップしていない場合は、「新しい機能をセットアップOffice 365 Message Encryption[を](set-up-new-message-encryption-capabilities.md)参照してください。

メール フロー ルールを構成するコンポーネントとメール フロー ルールの動作方法については、「メール フロー ルール (トランスポート ルール[)」](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)を参照Exchange Online。 Azure Information Protection でのメール フロー ルールの動作の詳細については、「Azure Information Protection ラベルExchange Onlineメール フロー ルールの構成」[を参照してください](/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> ハイブリッド Exchange環境では、オンプレミスのユーザーは、メールが OME 経由でルーティングされている場合にのみ、OME を使用して暗号化されたメールを送受信Exchange Online。 ハイブリッド Exchange 環境で OME を構成するには、ハイブリッド構成ウィザード[](/Exchange/exchange-hybrid)を使用してハイブリッドを構成してから[、Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server)から電子メール サーバーにメールをフローし、メール サーバーから Office 365 に流れるメールを構成する[必要があります](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。 メールが OME を通過するように構成Office 365、このガイダンスを使用して OME のメール フロー ルールを構成できます。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>新しい OME 機能を使用して電子メール メッセージを暗号化するメール フロー ルールを作成する

EAC を使用して、新しい OME 機能を使用してメッセージ暗号化をトリガーするメール フロー ルールを定義できます。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能を使用して電子メール メッセージを暗号化するルールを作成する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている仕事または学校のアカウントを使用して、管理者に[サインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365。

2. [管理] **タイルを選択** します。

3. Microsoft 365 管理センター で、**[管理センター]** \> **[Exchange]** の順に選択します。

4. EAC で、[メールフロー ルール] に移動し、[新しい新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。 EAC の使用の詳細については、「Exchange[管理センター」を参照](/exchange/exchange-admin-center)Exchange Online。

5. [ **名前]** に、ルールの名前を入力します (たとえば、メールの暗号化 DrToniRamos@hotmail.com。

6. [ **このルールを適用する場合**] で条件を選択し、必要に応じて値を入力します。 たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。

   1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。

   2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。

      - 既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。

      - 新しい名前を入力するには、[チェック名] ボックスに電子メール アドレス **を** 入力し、[名前の確認] \> **を選択します。[OK] を選択します**。

7. 条件を追加するには、[その他のオプション] **を選択** し、[条件の追加] **を選択し** 、一覧から選択します。

   たとえば、受信者が組織の外部にある場合にのみルールを適用するには、[条件の追加] を選択し、[受信者が組織の外部 **/** 内部である] \>  \> **[OK] を選択します**。

8. 新しい OME 機能を使用して暗号化を有効にするには、[次の操作] から [メッセージ セキュリティの変更] を選択し、[セキュリティと権限の保護の適用Office 365 Message Encryption **選択します**。 一覧から RMS テンプレートを選択し、[保存]**を選択し****、[OK] を選択します**。
  
  テンプレートの一覧には、すべての既定のテンプレートとオプション、およびユーザーが作成したカスタム テンプレートが含Office 365。 リストが空の場合は、「新しい機能を設定する」でOffice 365 Message Encryption機能を使用して新しい機能を設定Office 365 Message Encryption[してください](set-up-new-message-encryption-capabilities.md)。 既定のテンプレートの詳細については、「Azure Information Protection 用テンプレートの構成と管理 [」を参照してください](/information-protection/deploy-use/configure-policy-templates)。 [転送しない] **オプションの詳細** については、「メールの [転送しないオプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 暗号化専用オプションの **詳細については、「** メールの [暗号化専用オプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

  別のアクションを **指定する場合** は、[アクションの追加] を選択できます。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>EAC を使用して既存のメール フロー ルールを更新し、新しい OME 機能を使用する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている仕事または学校のアカウントを使用して、管理者に[サインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365。

2. [管理] **タイルを選択** します。

3. Microsoft 365 管理センター で、**[管理センター]** \> **[Exchange]** の順に選択します。

4. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

5. メール フロー ルールの一覧で、変更するルールを選択して新しい OME 機能を使用し、[編集] アイコン ![ を選択します ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。

6. 新しい OME 機能を使用して暗号化を有効にするには、[次の操作を行う] から [メッセージ セキュリティの変更] を選択し、[セキュリティと権限の保護を適用する] **Office 365 Message Encryptionを選択します**。 一覧から RMS テンプレートを選択し、[保存] を **選択し****、[OK] を選択します**。

   テンプレートの一覧には、すべての既定のテンプレートとオプション、およびユーザーが作成したカスタム テンプレートが含Office 365。 リストが空の場合は[、「Azure Information Protection](set-up-new-message-encryption-capabilities.md)の上に構築された新しい Office 365 Message Encryption 機能のセットアップ」の説明に従って、新しい機能を使用して Office 365 Message Encryption をセットアップしてください。 既定のテンプレートの詳細については、「Azure Information Protection 用テンプレートの構成と管理 [」を参照してください](/information-protection/deploy-use/configure-policy-templates)。 [転送しない] オプションの詳細については、「メールの [転送しないオプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 暗号化専用オプションの詳細については、「メールの [暗号化のみオプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   別のアクションを **指定する場合** は、[アクションの追加] を選択できます。

7. [次の **操作] の一覧** から、[メッセージ セキュリティの変更] に割り当てられているすべてのアクションを削除します。以前のバージョンの \> **OME を適用します**。

8. 保存] を選択します。

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>新しい OME 機能を使用してメール メッセージの暗号化を削除するメール フロー ルールを作成する

EAC を使用して、新しい OME 機能を使用してメッセージの削除暗号化をトリガーするメール フロー ルールを定義できます。

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能を使用して電子メール メッセージから暗号化を削除するルールを作成する

組織によって適用される暗号化を削除できます。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている仕事または学校のアカウントを使用して、管理者に[サインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365。

2. [管理] **タイルを選択** します。

3. Microsoft 365 管理センター で、**[管理センター]** \> **[Exchange]** の順に選択します。

4. EAC で、[メールフロー ルール] に移動し、[新しい新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。 EAC の使用の詳細については、「Exchange[管理センター」を参照](/exchange/exchange-admin-center)Exchange Online。

5. [ **名前]** に、送信メールから暗号化を削除するなどのルールの名前を入力します。

6. [ **このルールを適用する場合**] で、メッセージから暗号化を削除する条件を選択します。 [**追加] 送信者は、メール** を送信する組織の内部にあるか、受信者がメールを受信するために組織の \>  \> 内部に位置します。

7. [**次の操作を行う**] で、[**メッセージ セキュリティの** 変更] \> **を選択し、[Office 365 Message Encryption権限の保護] を選択します**。

8. **[保存]** を選択します。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>新しい機能を使用せずにOffice 365 Message Encryptionメール フロー ルールを作成する

組織を新しい OME 機能にまだ移動していない場合は、組織に妥当な場合は、すぐに新しい OME 機能に移行する計画を立てをお勧めします。 手順については、「Azure Information Protection の上にOffice 365 Message Encryption新しい機能をセットアップ[する」を参照してください](set-up-new-message-encryption-capabilities.md)。 それ以外の場合は、「新しい OME 機能を使用しないOffice 365 Message Encryptionメール フロー ルールの定義[」を参照してください](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)。

## <a name="related-topics"></a>関連項目

[Office 365 での暗号化](encryption.md)

[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)

[暗号化メッセージへのブランドの追加](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online のメール フロー ルール (トランスポート ルール)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

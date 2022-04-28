---
title: Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: ディレクトリ同期を使用してユーザーをMicrosoft 365にプロビジョニングする準備をする方法と、この方法を使用する長期的な利点について説明します。
ms.openlocfilehash: 03182d4cb0e9ed1da2687ab23ffae11369f3765a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090775"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ハイブリッド ID モデルを選択し、 [手順 2](protect-your-global-administrator-accounts.md) の管理者アカウントとこのソリューションの [手順 3](microsoft-365-secure-sign-in.md) のユーザー アカウントの保護を構成した場合、次のタスクはディレクトリ同期をデプロイすることです。 組織のディレクトリ同期の利点は次のとおりです。

- 組織内の管理プログラムを減らす
- 必要に応じてシングル サインオン シナリオを有効にする
- Microsoft 365でのアカウント変更の自動化

ディレクトリ同期を使用する利点の詳細については、[Azure Active Directory (Azure AD) を使用したハイブリッド ID](/azure/active-directory/hybrid/whatis-hybrid-identity) に関するページを参照してください。

ただし、ディレクトリ同期には、Active Directory Domain Services (AD DS) がMicrosoft 365 サブスクリプションのAzure AD テナントに同期され、最小限のエラーが発生するように計画と準備が必要です。

最適な結果を得るには、次の手順に従います。

> [!NOTE]
> 非 ASCII 文字は、AD DS ユーザー アカウント上のどの属性にも同期されません。

## <a name="ad-ds-preparation"></a>AD DS の準備

同期を使用してMicrosoft 365にシームレスに移行できるようにするには、Microsoft 365 ディレクトリ同期の展開を開始する前に、AD DS フォレストを準備する必要があります。
  
ディレクトリの準備は、次のタスクに重点を置く必要があります。

- 重複する **proxyAddress** 属性と **userPrincipalName** 属性を削除します。
- 有効な **userPrincipalName** 属性を使用して、空白の無効な **userPrincipalName** 属性を更新します。
- **givenName**、surname ( **sn**)、**sAMAccountName**、**displayName**、**mail**、**proxyAddresses**、**mailNickname**、**userPrincipalName** 属性の無効で疑問のある文字を削除します。 属性の準備の詳細については、「[Azure Active Directory同期ツールによって同期される属性の一覧](https://go.microsoft.com/fwlink/p/?LinkId=396719)」を参照してください。

    > [!NOTE]
    > これらは、同期Azure AD Connect同じ属性です。 
  
## <a name="multi-forest-deployment-considerations"></a>マルチフォレスト展開に関する考慮事項

複数のフォレストと SSO オプションの場合は、[Azure AD Connectのカスタム インストール](/azure/active-directory/hybrid/how-to-connect-install-custom)を使用します。
  
組織に認証用の複数のフォレスト (ログオン フォレスト) がある場合は、次のことを非常に推奨します。
  
- **フォレストの統合を検討してください。** 一般に、複数のフォレストを維持するために必要なオーバーヘッドが増えます。 組織に個別のフォレストの必要性を示すセキュリティ制約がない限り、オンプレミス環境の簡素化を検討してください。
- **プライマリ ログオン フォレストでのみ使用します。** Microsoft 365の初期ロールアウトについては、プライマリ ログオン フォレストにのみMicrosoft 365を展開することを検討してください。 

マルチフォレスト AD DS デプロイを統合できない場合や、他のディレクトリ サービスを使用して ID を管理している場合は、Microsoft またはパートナーの協力を得てこれらを同期できる場合があります。
  
詳細については、「[Azure AD Connectのトポロジ](/azure/active-directory/hybrid/plan-connect-topologies)」を参照してください。
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>ディレクトリ同期に依存する機能
  
ディレクトリ同期は、次の機能に必要です。
  
- Azure AD シームレス シングル Sign-On (SSO)
- Skype共存
- 次のようなハイブリッド展開Exchange。
  - オンプレミスのExchange環境とMicrosoft 365間の完全共有グローバル アドレス一覧 (GAL)。
  - 異なるメール システムからの GAL 情報の同期。
  - Microsoft 365サービスオファリングにユーザーを追加および削除する機能。 これには、次のものが必要です。
  - 双方向同期は、ディレクトリ同期のセットアップ中に構成する必要があります。 既定では、ディレクトリ同期ツールはディレクトリ情報をクラウドにのみ書き込みます。 双方向同期を構成するときに、書き戻し機能を有効にして、限られた数のオブジェクト属性をクラウドからコピーし、ローカル AD DS に書き戻します。 書き戻しは、Exchange ハイブリッド モードとも呼ばれます。 
  - オンプレミスのExchangeハイブリッド展開
  - 一部のユーザー メールボックスをMicrosoft 365に移動し、他のユーザー メールボックスをオンプレミスに保持する機能。
  - オンプレミスのセーフ送信者とブロックされた送信者は、Microsoft 365にレプリケートされます。
  - 基本的な委任と電子メールの代理送信機能。
  - オンプレミスのスマート カードまたは多要素認証ソリューションが統合されています。
- 写真、サムネイル、会議室、セキュリティ グループの同期

## <a name="1-directory-cleanup-tasks"></a>1. ディレクトリクリーンアップ タスク

AD DS をAzure AD テナントに同期する前に、AD DS をクリーンアップする必要があります。

> [!IMPORTANT]
> 同期する前に AD DS クリーンアップを実行しないと、デプロイ プロセスに大きな悪影響を及ぼす可能性があります。 ディレクトリ同期、エラーの特定、および再同期のサイクルを実行するには、数日または数週間かかる場合があります。

AD DS で、Microsoft 365 ライセンスが割り当てられるユーザー アカウントごとに、次のクリーンアップ タスクを実行します。

1. **proxyAddresses** 属性で有効で一意の電子メール アドレスを確認します。

2. **proxyAddresses** 属性内の重複する値をすべて削除します。

3. 可能であれば、ユーザーのユーザー **オブジェクトの** **userPrincipalName** 属性に対して有効で一意の値を確認します。 最適な同期エクスペリエンスを実現するには、AD DS UPN が Azure AD UPN と一致していることを確認します。 ユーザーが **userPrincipalName** 属性の値を持っていない場合は、 **ユーザー** オブジェクトに **sAMAccountName** 属性の有効で一意の値を含める必要があります。 **userPrincipalName** 属性内の重複する値をすべて削除します。

4. グローバル アドレス一覧 (GAL) を最適に使用するために、AD DS ユーザー アカウントの次の属性の情報が正しいことを確認します。

   - givenName
   - surname
   - displayName
   - 役職
   - 部署
   - 事業所
   - 事業所電話番号
   - 携帯電話番号
   - FAX 番号
   - 番地
   - 都市
   - 都道府県
   - 郵便番号
   - 国または地域

## <a name="2-directory-object-and-attribute-preparation"></a>2. ディレクトリ オブジェクトと属性の準備

AD DS とMicrosoft 365の間のディレクトリ同期を正常に行うには、AD DS 属性が適切に準備されている必要があります。 たとえば、Microsoft 365環境と同期されている特定の属性で特定の文字が使用されないようにする必要があります。 予期しない文字では、ディレクトリ同期は失敗しませんが、警告が返される可能性があります。 無効な文字を指定すると、ディレクトリ同期が失敗します。

一部の AD DS ユーザーに 1 つ以上の重複属性がある場合も、ディレクトリ同期は失敗します。 各ユーザーには一意の属性が必要です。

準備する必要がある属性を次に示します。

- **displayName**

  - 属性がユーザー オブジェクトに存在する場合は、Microsoft 365と同期されます。
  - この属性がユーザー オブジェクトに存在する場合は、その値が必要です。 つまり、属性を空白にしないでください。
  - 最大文字数: 256 文字

- **givenName**

  - 属性がユーザー オブジェクトに存在する場合は、Microsoft 365と同期されますが、Microsoft 365はそれを必要としたり使用したりすることはありません。
  - 最大文字数: 64 文字

- **mail**

  - 属性値は、ディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 重複する値がある場合は、値を持つ最初のユーザーが同期されます。 後続のユーザーはMicrosoft 365に表示されません。 両方のユーザーがMicrosoft 365に表示されるようにするには、Microsoft 365の値を変更するか、AD DS の両方の値を変更する必要があります。

- **mailNickname** (Exchange エイリアス)

  - 属性値はピリオド (.) で始めることはできません。
  - 属性値は、ディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 同期された名前のアンダースコア ("_") は、この属性の元の値に無効な文字が含まれていることを示します。 この属性の詳細については、「[Exchangeエイリアス属性](/powershell/module/exchange/set-mailbox)」を参照してください。
    >

- **proxyAddresses**

  - Multiple-value 属性
  - 値あたりの最大文字数: 256
  - 属性値にスペースを含めることはできません。
  - 属性値は、ディレクトリ内で一意である必要があります。
  - 無効な文字: \< \> ( ) ; , [ ] "
  - umlauts、アクセント、チルドなどの発音記号を持つ文字は無効な文字です。

    無効な文字は、型区切り記号と ":" の後の文字に適用されます。SMTP:User@contso.com は許可されていますが、SMTP:user:M@contoso.com は許可されません。

    > [!IMPORTANT]
    > すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージング標準に準拠している必要があります。 重複するアドレスまたは不要なアドレスが存在する場合は削除します。

- **sAMAccountName**

  - 最大文字数: 20 文字
  - 属性値は、ディレクトリ内で一意である必要があります。
  - 無効な文字: [ \ " | 、 / : \< \> + = ; ? \* ']
  - ユーザーが無効な **sAMAccountName** 属性を持ち、有効な **userPrincipalName** 属性を持っている場合、ユーザー アカウントはMicrosoft 365に作成されます。
  - **sAMAccountName** と **userPrincipalName** の両方が無効な場合は、AD DS **userPrincipalName** 属性を更新する必要があります。

- **sn** (姓)

  - 属性がユーザー オブジェクトに存在する場合は、Microsoft 365と同期されますが、Microsoft 365はそれを必要としたり使用したりすることはありません。

- **targetAddress**

    ユーザーに設定された **targetAddress** 属性 (SMTP:tom@contoso.com など) を Microsoft 365 GAL に表示する必要があります。 サード パーティのメッセージング移行シナリオでは、AD DS のMicrosoft 365スキーマ拡張機能が必要になります。 Microsoft 365 スキーマ拡張機能では、AD DS のディレクトリ同期ツールを使用して設定されたMicrosoft 365 オブジェクトを管理するために、他の便利な属性も追加されます。 たとえば、非表示のメールボックスまたは配布グループを管理する **msExchHideFromAddressLists** 属性が追加されます。

  - 最大文字数: 256 文字
  - 属性値にスペースを含めることはできません。
  - 属性値は、ディレクトリ内で一意である必要があります。
  - 無効な文字: \ \< \> ( ) ; , [ ] "
  - すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージング標準に準拠している必要があります。

- **userPrincipalName**

  - **userPrincipalName** 属性は、ユーザー名の後に at sign (@) とドメイン名 (user@contoso.com など) が続くインターネット スタイルのサインイン形式である必要があります。 すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージング標準に準拠している必要があります。
  - **userPrincipalName** 属性の最大文字数は 113 です。 次のように、at 記号 (@) の前後に特定の文字数を指定できます。
  - at sign (@): 64 の前にあるユーザー名の最大文字数
  - at sign (@): 48 に続くドメイン名の最大文字数
  - 無効な文字: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - 許可される文字: A – Z、a - z、0 – 9、 ' . - _ ! # ^ ~
  - umlauts、アクセント、チルドなどの発音記号を持つ文字は無効な文字です。
  - 各 **userPrincipalName** 値には@文字が必要です。
  - @ 文字は、各 **userPrincipalName** 値の最初の文字にすることはできません。
  - ユーザー名はピリオド (.)、アンパサンド (&amp;)、スペース、または記号 (@) で終わることはできません。
  - ユーザー名にスペースを含めることはできません。
  - ルーティング可能なドメインを使用する必要があります。たとえば、ローカル ドメインまたは内部ドメインは使用できません。
  - Unicode はアンダースコア文字に変換されます。
  - **userPrincipalName** には、ディレクトリ内に重複する値を含めることはできません。

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. userPrincipalName 属性を準備する

Active Directory は、組織内のエンド ユーザーが **sAMAccountName** または **userPrincipalName** を使用してディレクトリにサインインできるように設計されています。 同様に、エンド ユーザーは職場または学校アカウントのユーザー プリンシパル名 (UPN) を使用してMicrosoft 365にサインインできます。 ディレクトリ同期では、AD DS にあるのと同じ UPN を使用して、Azure Active Directoryに新しいユーザーを作成しようとします。 UPN は電子メール アドレスのように書式設定されます。

Microsoft 365では、UPN は電子メール アドレスの生成に使用される既定の属性です。 **userPrincipalName** (AD DS とAzure AD) と **proxyAddresses** のプライマリ電子メール アドレスを異なる値に設定するのは簡単です。 異なる値に設定すると、管理者とエンド ユーザーが混乱する可能性があります。

混乱を減らすために、これらの属性を調整することをお勧めします。 Active Directory フェデレーション サービス (AD FS) (AD FS) 2.0 でのシングル サインオンの要件を満たすためには、Azure Active Directoryと AD DS の UPN が一致し、有効なドメイン名前空間を使用していることを確認する必要があります。

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. 代替 UPN サフィックスを AD DS に追加する

ユーザーの企業資格情報をMicrosoft 365環境に関連付けるには、代替の UPN サフィックスを追加する必要がある場合があります。 UPN サフィックスは、@ 文字の右側の UPN の一部です。 シングル サインオンに使用する UPN には文字、数字、ピリオド、ダッシュ、アンダースコアを含めることができますが、その他の種類の文字を含めることはできません。

代替 UPN サフィックスを Active Directory に追加する方法の詳細については、「 [ディレクトリ同期の準備](https://go.microsoft.com/fwlink/p/?LinkId=525430)」を参照してください。

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. AD DS UPN と Microsoft 365 UPN を一致させる

ディレクトリ同期を既に設定している場合、Microsoft 365のユーザーの UPN が、AD DS で定義されているユーザーの AD DS UPN と一致しない可能性があります。 ドメインが確認される前にユーザーにライセンスを割り当てた場合、この状況が発生することがあります。 これを修正するには、[PowerShell を使用して重複する UPN を修正](https://go.microsoft.com/fwlink/p/?LinkId=396730)し、ユーザーの UPN を更新して、Microsoft 365 UPN が会社のユーザー名とドメインと一致することを確認します。 AD DS で UPN を更新していて、Azure Active Directory ID と同期する場合は、AD DS で変更を行う前に、Microsoft 365でユーザーのライセンスを削除する必要があります。

ディレクトリ [同期のためにルーティング不可能なドメイン (.local ドメインなど) を準備する方法](prepare-a-non-routable-domain-for-directory-synchronization.md)についても説明します。

## <a name="next-steps"></a>次の手順

上記の 1 ~ 5 を完了したら、「 [ディレクトリ同期を設定](set-up-directory-synchronization.md)する」を参照してください。

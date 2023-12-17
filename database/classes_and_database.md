# Classes and DATABASE

*Updated: 2023-08-17*

## { Classes }

- 📁 **User.ts**
    
    ```tsx
    export class User {
    
        constructor(
    
            private user_name: string,
            private address: string,
            private phone_number: string,
            private cpf: string,
            private registration_date: Date
    
        ) {
    
        }
    
        getName(): string {
            return this.user_name;
        }
    
        getAdress(): string {
            return this.address;
        }
    
        getPhoneNumber(): string {
            return this.phone_number;
        }
    
        getCpf(): string {
            return this.cpf
        }
    
        getRegistrationDate(): Date {
            return this.registration_date;
        }
    
    }
    ```
    
- 📁 **EmergencyRequest.ts**
    
    ```tsx
    export class EmergencyRequest{
    
        protected request_time: Date; 
        protected latitude: string; 
        protected longitude: string;
        protected notification_message: string; 
        protected userId: number; 
        protected statusId: number; 
    
        constructor(){}
    
        getRequestTime(): Date{
            return this.request_time; 
        }
    
        getLatitude(): string {
            return this.latitude; 
        }
    
        getLongitude(): string {
            return this.longitude; 
        }
    
        getNotificationMessage():string {
            return this.notification_message;
        }
    
        getUserId():number{
            return this.userId; 
        }
    
        getStatusId(): number {
            return this.statusId;
        }
    
    }
    ```
    
- 📁 **Contacts.ts**
    
    ```tsx
    export class Contacts { 
    
        private userId:number; 
        constructor (
            private contact_name: string, 
            private contact_phone: string, 
            private contact_type: string
        )
        {
    
        }
    
        getContactName(): string {
            return this.contact_name;
        }
    
        getContactPhone(): string { 
            return this.contact_phone; 
        }
    
        getContactType(): string {
            return this.contact_type; 
        }
    
        getUserId(): number {
            return this.userId; 
        }
        
    }
    ```
    
- 📁 **EmergencyRequestStatus.ts**
    
    ```tsx
    import { EmergencyRequest } from "./EmergencyRequest";
    
    export class EmergencyRequestStatus extends EmergencyRequest {
    
        private statusName: string; 
    
        constructor () {
            super()
        }
    
        getStatusName():string {
            return this.statusName; 
        }
    
    }
    ```
    

## { Database }

- 📁 **Database.ts**

## { Test }

<aside>
💡 https://mariadb.com/kb/en/getting-started-with-the-nodejs-connector/

</aside>

## { Zip Database }

[bah-socorro_database-2023.08.17.zip](Classes%20and%20DATABASE%20606c87f2b6cf4265846d861651784383/bah-socorro_database-2023.08.17.zip)
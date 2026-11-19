# Meep

Desarrollo de MEEP, una app para explorar mediciones de pH en alimentos.

## Inicio de sesión

`index.html` es la entrada de la aplicación. Permite crear una cuenta e iniciar sesión con Supabase Auth; al autenticar correctamente, lleva a `Aplicación Meep.html`. Las sesiones se mantienen mediante Supabase Auth.

## Configuración de Supabase

La URL y la clave publicable del proyecto se configuran en `index.html`. Ejecuta [`supabase/schema.sql`](supabase/schema.sql) en **Supabase → SQL Editor** para crear la tabla de mediciones y sus políticas de seguridad (RLS). Las credenciales de usuario las administra Supabase Auth; nunca guardes contraseñas en una tabla propia ni publiques una `service_role` key.

El archivo SQL prepara el almacenamiento privado de mediciones. La integración de sincronización del historial de la app con esa tabla todavía debe implementarse; por ahora, el historial existente continúa guardándose en el navegador.
